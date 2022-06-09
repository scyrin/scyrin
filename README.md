<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BSCS3D</title>
</head>
<body>
    <?php
    use PHPMailer\PHPMailer\PHPMailer;
    use PHPMailer\PHPMailer\SMTP;
    use PHPMailer\PHPMailer\Exception;
    
    require 'vendor/autoload.php';

    $mail = new PHPMailer(true);

    try{
        //setup Server
        $mail->isSMTP();
        $mail->Host = 'smtp.gmail.com';
        $mail->SMTPAuth = true;
        $mail->Username = 'lordedgardian@gmail.com';
        $mail->Password = 'secret';
        $mail->SMTPSecure = PHPMailer::ENCRYPTION_SMTPS;   
        $mail->Port = 465;
        //setup email
        $mail->setFrom('lordedgardian@gmail.com' , 'Tavu Corp.');
        $mail->addAddress('tavulordedgardian@plmun.edu.ph');
        $mail->isHTML(true);
        $mail->Subject = 'Application: Hired';
        $mail->Body = "Hi <b>audrey</b>!<br>
            I'm pleased to inform you that your application to Tavu Corporation is <i>accepted</i><br>
            We're expecting your presence tomorrow at exactly <b>8:00AM</b><br><br>
            We're glad and excited to work with you<br>
            Thank you. Regards";
        $mail->send();
        echo 'Message has been sent';
    }catch(Exception $e){
        echo "Message could not be sent. Mailer Error: {$mail->ErrorInfo}";
    }
    ?>
</body>
</html>

