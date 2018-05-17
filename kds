<!DOCTYPE html>

<html>

<head>

      <title>Karar Destek Sistemleri</title>

      <meta charset="utf-8">

      <meta name="viewport" content="width=device-width,initial-scale=1">

      <link href="stil.css" rel="stylesheet">

      <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.0/css/bootstrap.min.css" integrity="sha384-9gVQ4dYFwwWSjIDZnLEWnxCjeSWFphJiwGPXr1jddIhOegiu1FwO5qRGvFXOdJZ4" crossorigin="anonymous">

<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.0/js/bootstrap.min.js" integrity="sha384-uefMccjFJAIv6A+rW+L4AHf99KvxDjWSu1z9VI8SKNVmz4sk7buKt/6v9KI65qnm" crossorigin="anonymous"></script>

</head>

<body>

    <body style="background:url(tarla.jpg) top center no-repeat;">
	
	
    <div class="container" style="width:5000px;height:1500px;">

 

<form class="form-signin" method="POST" action="index.php">

<h2 class="form-signin-heading"><strong><center><p>Tarım Karar Destek Sistemi</p></center></strong></h2>



<select class="form-control selectpicker" name="il" id="il" style="margin-left:350px; ;margin-top: 350px;width: 400px;height: 40px;">

 <option value="İl seçiniz">İl seçiniz</option>
 <option value="7">antalya</option>

  <option value="35">izmir</option>

    <option value="59">tekirdağ</option>

 

  <option value="52">ordu</option>

    <option value="44">malatya</option>

 

</select>

<select class="form-control selectpicker" name="ilce" id="ilce" style="margin-left:350px; ;margin-top: 50px;width: 400px;height: 40px;">

  
 <option value="İlçe seçiniz">İlçe seçiniz</option>
 <option value="371">Finike</option>

<option value="72">Akseki</option>

<option value="73">Korkuteli</option>

<option value="351">Bergama</option>

<option value="352">Seferihisar</option>

<option value="353">Selçuk</option>

<option value="354">Kiraz</option>

<option value="355">Ödemiş</option>

<option value="441">Arguvan</option>

<option value="442">Derende</option>

<option value="443">Pötürge</option>

<option value="521">Ünye</option>

<option value="522">Mesudiye</option>

<option value="523">Akkuş</option>

<option value="591">Malkara</option>

<option value="592">Ergene</option>

<option value="593">Çorlu</option>

</select>

<select class="form-control selectpicker" name="aylar" id="aylar" style="margin-left:350px; ;margin-top: 50px;width: 400px;height: 40px;">

  
  <option value="ay seçiniz">Ay seçiniz</option>
  <option value="1">Ocak</option>

  <option value="2">Şubat</option>

  <option value="3">Mart</option>

<option value="4">Nisan</option>

<option value="5">Mayıs</option>

<option value="6">Haziran</option>

<option value="7">Temmuz</option>

<option value="8">Ağustos</option>

<option value="9">Eylül</option>

<option value="10">Ekim</option>

<option value="11">Kasım</option>

<option value="12">Aralık</option>

 

</select>

<button class="btn-primary" type="submit" style="margin-left:350px; ;margin-top: 50px;width: 400px;height: 40px;">SORGULA</button>

</form>

 

 

 

<table class="table table-hover table-bordered text-white bg-primary  " style="margin-left:130px; ;margin-top: 100px;width: 800px;height: 40px;">

        <thead>

            <tr>

                <td>İl Adı</td>

                <td>İlçe Adı</td>

                                                               <td>Ay</td>

                                                               <td>Toprak Çeşidi</td>

                                                               <td>Yağış Miktarı</td>

                                                               <td>Sıcaklık</td>

                                                              

            </tr>

        </thead>

        <tbody>

 

        <?php

                               $il=$_POST["il"];

                               $ilce=$_POST["ilce"];

                               $ay=$_POST["aylar"];

 

                                               $sorgu="SELECT il.il_ad, ilce.ilce_ad, aylar.ay_ad,topraklar.toprak_ad,yagislar.miktar,sicaklik.derece

FROM il, il_ilce, ilce, aylar, topraklar, yagislar, sicaklik

WHERE il.il_id=il_ilce.il_id AND il_ilce.ilce_id=ilce.ilce_id AND topraklar.ilce_id=ilce.ilce_id AND yagislar.ilce_id=ilce.ilce_id AND aylar.ay_id=yagislar.ay_id AND aylar.ay_id=sicaklik.ay_id AND sicaklik.ilce_id=ilce.ilce_id AND il.il_id=$il AND ilce.ilce_id=$ilce AND aylar.ay_id=$ay";

            $connect=mysqli_connect("localhost","root","","kds2001");

                                               mysqli_query($connect,"SET CHARACTER SET 'utf8'");

                                               mysqli_query($connect,"SET SESSION collation_connection ='utf8_unicode_ci'");

                                              

            if (!$connect) {

                die(mysqli_error());

            }

           

            $results = mysqli_query($connect,$sorgu);

            while($row = mysqli_fetch_array($results)) {

            ?>

 

                <tr>

                    <td><?php echo $row['il_ad']?></td>

                    <td><?php echo $row['ilce_ad']?></td>

                                                                               <td><?php echo $row['ay_ad']?></td>

                                                                               <td><?php echo $row['toprak_ad']?></td>

                                                                               <td><?php echo $row['miktar']?></td>

                                                                               <td><?php echo $row['derece']?></td>

                </tr>

            <?php

            }

            ?>

            </tbody>

            </table>

                 

                  

</div>

 

</body>

</html>
