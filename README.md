<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
<script>
function convertToUTC(timeStamp) {
  var year = timeStamp.substring(0, 4);
  var month = timeStamp.substring(5, 7);
  var day = timeStamp.substring(8, 10);
  var hrs = timeStamp.substring(11, timeStamp.indexOf(":"));
  var mins = timeStamp.substring(14, 16);
  var secs = timeStamp.substring(17);

  var t = new Date(year, month - 1, day, hrs, mins, secs);
  year = t.getUTCFullYear();
  month = checkTime(t.getUTCMonth() + 1);
  day = checkTime(t.getUTCDate());
  hrs = checkTime(t.getUTCHours());
  mins = checkTime(t.getUTCMinutes());
  secs = checkTime(t.getUTCSeconds());

  return year + "-" + month + "-" + day + " " + hrs + ":" + mins + ":" + secs;
}
function sth(localTimeRange) {
  utcTime = convertToUTC(localTimeRange.substr(0,10)+ " 00:00:00") + " - " + convertToUTC(localTimeRange.substr(13,10)+ " 23:59:59")
  document.getElementById("test").innerHTML = utcTime;
}

function checkTime(i) {
    if (i < 10) {i = "0" + i};  // add zero in front of numbers < 10
    return i;
}
</script>
</head
>
<body>
  <div>
    <div>
        <button type="button" onclick="sth('2018-11-11 - 2018-11-11')">CLick</button>
        <p id="test"></p>
    </div>
  </div>

</body> 
</html>

