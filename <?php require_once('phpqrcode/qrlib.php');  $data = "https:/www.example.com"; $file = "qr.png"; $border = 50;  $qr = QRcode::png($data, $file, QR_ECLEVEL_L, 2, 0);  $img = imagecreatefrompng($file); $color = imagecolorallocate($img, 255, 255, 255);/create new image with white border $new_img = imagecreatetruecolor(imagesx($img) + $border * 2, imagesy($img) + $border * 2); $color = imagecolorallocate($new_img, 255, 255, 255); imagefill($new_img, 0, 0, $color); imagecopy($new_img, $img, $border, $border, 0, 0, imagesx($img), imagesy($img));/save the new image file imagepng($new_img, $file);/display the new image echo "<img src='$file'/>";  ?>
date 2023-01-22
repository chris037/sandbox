<?php
require_once('phpqrcode/qrlib.php');

$data = "https://www.example.com";
$file = "qr.png";
$border = 50;

$qr = QRcode::png($data, $file, QR_ECLEVEL_L, 2, 0);

$img = imagecreatefrompng($file);
$color = imagecolorallocate($img, 255, 255, 255);

// create new image with white border
$new_img = imagecreatetruecolor(imagesx($img) + $border * 2, imagesy($img) + $border * 2);
$color = imagecolorallocate($new_img, 255, 255, 255);
imagefill($new_img, 0, 0, $color);
imagecopy($new_img, $img, $border, $border, 0, 0, imagesx($img), imagesy($img));

// save the new image file
imagepng($new_img, $file);

// display the new image
echo "<img src='$file'/>";

?>
