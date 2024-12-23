# mpdf-bangla-font-nikhosh
# open config_fonts.php file and change 
 $this->fontdata = array(
"nikosh" => array(
        'R' => "Nikosh.ttf",
        'useOTL' => 0xFF,
    ),
)
# open pdf file
change this font 
<style>
        body{
        font-family: nikosh, sans-serif;
    }
#as like
$mpdf = new mPDF('','A4',16,'nikosh');
$mpdf->SetProtection(array('print'));
$mpdf->SetTitle($type . " | Developed By BSD");
$mpdf->SetAuthor("BSD");
$mpdf->SetDisplayMode('fullpage');

$xhtml = '<html>
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

        <!-- External CSS -->
        <link rel="stylesheet" href="css/bootstrap.css">
        <link rel="stylesheet" href="css/style.css">
        <style>
        body{
        font-family: nikosh, sans-serif;
    }
    </style>
        </head>
        <body>
        
            <div class="contain">
                ' . $mainbody . '
            </div><!-- Contain -->
            
        </body>
    </html>';

//echo $xhtml;

$mpdf->WriteHTML($xhtml);
$mpdf->Output();
