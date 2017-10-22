function calc() {
  
  var res = 0;
  var m1 = parseInt($("#m1").val());
  var m2 = parseInt($("#m2").val());
  var m3 = parseInt($("#m3").val());
  var m4 = parseInt($("#m4").val());
  var m5 = parseInt($("#m5").val());
  var m6 = parseInt($("#m6").val());
  var c1 = parseInt($("#c1").val());
  var c2 = parseInt($("#c2").val());
  var c3 = parseInt($("#c3").val());
  var c4 = parseInt($("#c4").val());
  var s1 = parseInt($("#s1").val());
  var s2 = parseInt($("#s2").val());
  var s3 = parseInt($("#s3").val());
  var s4 = parseInt($("#s4").val());
  var v1 = parseInt($("#v1").val());
  var v2 = parseInt($("#v2").val());
  var v3 = parseInt($("#v3").val());
  var v4 = parseInt($("#v4").val());
  var o1 = parseInt($("#o1").val());
  var o2 = parseInt($("#o2").val());
  var o3 = parseInt($("#o3").val());
  var o4 = parseInt($("#o4").val());
  var size = 0;
  var testo = 0;
 
  
  if(m1+m2+m3+m4+m5+m6+c1+c2+c3+c4+s1+s2+s3+s4+v1+v2+v3+v4+o1+o2+o3+o4>15){
    $("#result").text("Слишком много ингридиентов. Выберете не более 15.");
  }   
  else{
    if( m1>3||m2>3||m3>3||m4>3||m5>3||m6>3||c1>3||c2>3||c3>3||c4>3||s1>3||s2>3||s3>3||s4>3||v1>3||v2>3||v3>3||v4>3||o1>3||o2>3||o3>3||o4>3){ $("#result").text("Мы не можем положить больше трех порций одного ингридиента.");}
  else{ 
  if ($("#size").val() == "18cm") {
    size += 200;
  }
  else if($("#size").val() == "20cm") {
    size += 220;
  }
  else{
    size += 250;
  }
  
  if ($("#testo").val() == "1") {
    testo += 1;
  }
  else if($("#testo").val() == "2") {
    testo += 1.1;
  }
  else{
    testo += 1.15;
  }
   res=(m1+m2+m3+m4+m5+m6)*20+(c1+c2+c3+c4)*30+(s1+s2+s3+s4)*10+(v1+v2+v3+v4)*15+(o1+o2+o3+o4)*30+testo*size;
  
  
    
  if ($("#home").is(":checked")) {
    if(res<400){
        res += 200;
    }
  } $("#result").text(Math.round(res)+"руб.");}
}}
$("#main").change(calc);
calc();