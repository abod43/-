ob_start();
$API_KEY = "55555:0000"; #2140104762:AAFtnov0K4I6WRQgRxUWgX1NJzbjIdol4dg
define('API_KEY',$API_KEY);
echo "<a href='https://api.telegram.org/bot$API_KEY/setwebhook?url=".$_SERVER['SERVER_NAME']."".$_SERVER['SCRIPT_NAME']."'>setwebhook</a>";
echo file_get_contents("https://api.telegram.org/bot$API_KEY/getme?url=".$_SERVER['SERVER_NAME']."".$_SERVER['SCRIPT_NAME']);
function bot($method,$datas=[]){
$url = "https://api.telegram.org/bot".API_KEY."/".$method;
$ch = curl_init();
curl_setopt($ch,CURLOPT_URL,$url); curl_setopt($ch,CURLOPT_RETURNTRANSFER,true);
curl_setopt($ch,CURLOPT_POSTFIELDS,$datas);
$res = curl_exec($ch);
if(curl_error($ch)){
var_dump(curl_error($ch));
}else{return json_decode($res);}}
#     @SeroBots     #
$update = json_decode(file_get_contents('php://input'));
@$message = $update->message;
@$from_id = $message->from->id;
@$chat_id = $message->chat->id;
@$message_id = $message->message_id;
@$first_name = $message->from->first_name;
@$last_name = $message->from->last_name;
@$username = $message->from->username;
@$text= $message->text;
@$firstname = $update->callback_query->from->first_name;
@$usernames = $update->callback_query->from->username;
@$chatid = $update->callback_query->message->chat->id;
@$fromid = $update->callback_query->from->id;
$message  = $update->message;
$settings = json_decode(file_get_contents("wiki.json"),true);
$text    = $message->text;
 $data = $update->callback_query->data;
$chat_id  = $message->chat->id;
$name   = $message->from->first_name;
$from_id = $message->from->id;
$u = explode("\n",file_get_contents("memb.txt"));
$c = count($u)-1;
$modxe = file_get_contents("usr.txt");
mkdir("bero");
mkdir('data');
//2
date_default_timezone_set('Asia/Baghdad');
$today = date("l");
$nmonth = date("m");
$times = date("h:i");
$year = date("Y");

switch ($today) 
{
case "Saturday":  
$today="السبت"; 
break; 
case "Sutoday":  
$today="الأحد"; 
break;  
case "Motoday":  
$today="الاثنين"; 
break; 
case "Tuesday":  
$today="الثلاثاء"; 
break; 
case "Wednesday": 
$today="الأربعاء"; 
break; 
case "Thursday":  
$today="الخميس"; 
break; 
case "Friday":  
$today="الجمعة"; 
break; 
}  
switch ($nmonth){
case 1: $nmonth="كانون الثاني";
break;
case 2: $nmonth="شباط";
break;
case 3: $nmonth="أذار";
break;
case 4: $nmonth="نيسان";
break;
case 5: $nmonth="أيار";
break;
case 6: $nmonth="حزيران";
break;
case 7: $nmonth="تموز";
break; 
case 8: $nmonth="أب";
break;
case 9: $nmonth="أيلول";
break;
case 10: $nmonth="تشرين الأول";
break;
case 11: $nmonth="تشرين الثاني";
break;
case 12: $nmonth="كانون الأول";
break;
} 

//3
if($update){

}
// 4

$bero2 = $message->message_id;
$bero20= file_get_contents("https://api.telegram.org/bot$API_KEY/getChatMember?chat_id=$chat_id&user_id=".$from_id);
$bero21= json_decode($bero20, true);
$bero22 = $bero21['result']['status'];
$ch = file_get_contents("bero/$chat_id.txt");
$setklesha = file_get_contents("bero/modsetkle$chat_id.txt");
$myklish = file_get_contents("bero/setkle$chat_id.txt");
$name_tg = "[$name](tg://user?id=$from_id)";

$a = str_replace('#name',"$first_name",$myklish);
$a = str_replace('#id',$from_id,$a);
$a = str_replace('#name_user',$name_tg,$a);
$a = str_replace('#username',$username,$a);
$a = str_replace('#ch',$ch,$a);
$a = str_replace('#ch2',$ch2,$a);
$g = $a;

if($setklesha == null){
$mytext = " - [$name](tg://user?id=$from_id) ؛ ❤️

- لايمكنك ارسال اي رسالة هنا لانك غير مشترك في قناة المجموعة ؛ ✅

- اشترك الان من هنا ؛ [@$ch] 📡
";
}

if($setklesha == "yes"){
$mytext = $g;
}
$ckl = "@seropubg"; 
$ch2 = file_get_contents("https://api.telegram.org/bot$API_KEY/getChatMember?chat_id=@$ch&user_id=".$from_id);
$getch2 = json_decode(file_get_contents("http://api.telegram.org/bot$API_KEY/getChat?chat_id=@$ch"))->result;
$Namech2 = $getch2->title;
$join = file_get_contents("https://api.telegram.org/bot".API_KEY."/getChatMember?chat_id=@$ch&user_id=".$from_id);
if($message && (strpos($join,'"status":"left"') or strpos($join,'"Bad Request: USER_ID_INVALID"') or strpos($join,'"status":"kicked"'))!== false){
if($bero22 != "creator" and $bero22 != "administrator"){
bot('DeleteMessage',[
'chat_id'=>$chat_id,
'message_id'=>$bero2
]);
bot('sendMessage', [
'chat_id'=>$chat_id,
'text'=>"
$mytext
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
    [['text'=>"$Namech2",'url'=>"https://t.me/$ch"]]
]
])
]);return false;}}

$ch22bt = file_get_contents("bero/2$chat_id.txt");
$ckl = "@seropubg"; 
$ch2 = file_get_contents("https://api.telegram.org/bot$API_KEY/getChatMember?chat_id=@$ch22bt&user_id=".$from_id);
$getch2 = json_decode(file_get_contents("http://api.telegram.org/bot$API_KEY/getChat?chat_id=@$ch22bt"))->result;
$Namech2 = $getch2->title;
$join = file_get_contents("https://api.telegram.org/bot".API_KEY."/getChatMember?chat_id=@$ch22bt&user_id=".$from_id);
if($message && (strpos($join,'"status":"left"') or strpos($join,'"Bad Request: USER_ID_INVALID"') or strpos($join,'"status":"kicked"'))!== false){
if($bero22 != "creator" and $bero22 != "administrator"){
bot('DeleteMessage',[
'chat_id'=>$chat_id,
'message_id'=>$bero2
]);
bot('sendMessage', [
'chat_id'=>$chat_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

- لايمكنك ارسال اي رسالة هنا لانك غير مشترك في قناة المجموعة ؛ ✅

- اشترك الان من هنا ؛ [@$ch22bt] ✮ ",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
    [['text'=>"$Namech2",'url'=>"https://t.me/$ch22bt"]]
]
])
]);return false;}}


$ch2 = file_get_contents("bero/r$chat_id.txt");
$ch22 = file_get_contents("bero/r2$chat_id.txt");

$setklesha1 = file_get_contents("bero/modsetkle1$chat_id.txt");
$myklish1 = file_get_contents("bero/setkle1$chat_id.txt");
if($setklesha1 == null){
$mytext = "  - [$name](tg://user?id=$from_id) ؛ ❤️

لايمكنك ارسال اي رسالة هنا لانك غير مشترك في حساب المجموعه ؛ ✅


- اشترك الان من هنا ؛ ✳
$ch2
";
}

if($setklesha1 == "yes"){
$mytext1 = $myklish1;
}

$url = file_get_contents("data/$from_id.".txt."","0");
if($ch22 == "on"){
if($text and $url !=2){
 file_put_contents("data/$from_id.".txt."",$url+1);
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>" $myklish1
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
]);return false;
}
}



$bero = explode("\n",file_get_contents("bero2.txt"));

$bero2 = count($bero)-1;

$SA3end = explode("\n",file_get_contents("ber9o.txt"));

$ber9o = count($SA3end)-1;

$bero2Files; //1497161818

@$tc = $update->message->chat->type;1497161818 

$ckl = "@serobots"; 
$ch2 = file_get_contents("https://api.telegram.org/bot$API_KEY/getChatMember?chat_id=".$ckl."&user_id=".$from_id);
$getch2 = json_decode(file_get_contents("http://api.telegram.org/bot$API_KEY/getChat?chat_id=".$ckl))->result;
$Namech2 = $getch2->title;
$getch2li = str_replace("@","",$ckl);
$Alsh = $API_KEY; #توكن البوت الرفعته ادمن
$ali = $ckl; #معرف قناتك
$join = file_get_contents("https://api.telegram.org/bot".$Alsh."/getChatMember?chat_id=$ali&user_id=".$from_id);
if($tc == "private") {
if($message && (strpos($join,'"status":"left"') or strpos($join,'"Bad Request: USER_ID_INVALID"') or strpos($join,'"status":"kicked"'))!== false){
bot('sendMessage',['chat_id'=>$chat_id,
'text'=>"
انت غير مشترك بقنوات البوت △
اشترك ثم ارسل /start 
 - [$Namech2](https://t.me/$getch2li)
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
 'reply_to_message_id'=>$message->message_id,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>$Namech2,'url'=>"https://t.me/$getch2li"]],
]])
]);return false;}}

if($text == "/start"){
if($tc == "private") {
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"- [$name](tg://user?id=$from_id) ؛ 👮‍♂

- اهلا بك في بوت ويادة اعضاء قناتك من خلال مجموعتك ؛ 👥

- اضفني الى مجموعتك وقم برفعي مشرف ؛ 👨‍✈️

- بعدها ارسل { تفعيل البوت } واتبع التعليمات التي ارسلها اليك ؛ 🈯️

- لتعطيل البوت ارسل داخل مجموعتك كلمة { تعطيل البوت } ؛ ❎
- لاضهار اوامر البوت ارسل كلمة { الاوامر } داخل مجموعتك ؛ 🤖
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
    [['text'=>"اضافه البوت 👾",'url'=>"https://t.me/nt7Bot?اشترلك الاجياريgroup=Commands&admin=delete_messages+apin_messages+invite_users"]],
    [['text'=>"<  عدد مستخدمين البوت الكلي : $bero2 >",'url'=>"https://t.me/SeroBots"]],
]
])
]);
if ($update && !in_array($chat_id, $u)) {
    file_put_contents("memb.txt", $chat_id."\n",FILE_APPEND);
  }
  }
}

$klish = file_get_contents("bero/setkle$chat_id.txt");
if($text == "testbero"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"
$klish
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_markup'=>json_encode([
'inline_keyboard'=>[
    [['text'=>"اضافه البوت 👾",'url'=>"https://t.me/nt7Bot?اشترلك الاجياريgroup=Commands&admin=delete_messages+apin_messages+invite_users"]],
    [['text'=>"<  عدد مستخدمين البوت الكلي : $bero2 >",'url'=>"https://t.me/SeroBots"]],
]
])
]);
}
if($bero22 == "creator" or $bero22 == "administrator" ){
$S = file_get_contents("bero/S$chat_id $from_id.txt");
if($text == "تفعيل البوت"){

file_put_contents("bero/S$chat_id $from_id.txt", "1");
file_put_contents("bero/$chat_id.txt", "");
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

- الان ارسل معرف قناة المجموعة التي لايمكن للاعضاء التكلم فيها الى بعد الاشتراك فيها ؛ ✅

- ملاحظة : ارسل معرف القناة بدون { @ } ؛ ⁉️
- مثال ؛ [$kna] ؛ ☑️",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}

}


$MEMH = bot('getchatmemberscount',['chat_id'=>$chat_id])->result;
$link = bot("getchat",['chat_id'=>$chat_id])->result->invite_link;
if($link != null){
  $link = $link;
$link2 = $link;
  }else{
   $link = bot("exportChatInviteLink",['chat_id'=>$chat_id])->result;
$link2 = $link;
   }
$add = $settings["information"]["added"];
$MEMH = bot('getchatmemberscount',['chat_id'=>$chat_id])->result;
if($text and $S == "1"){
file_put_contents("bero/$chat_id.txt", "$text");
file_put_contents("bero/S$chat_id $from_id.txt", "");
file_put_contents("bero/r20$chat_id.txt", "on");
file_put_contents("bero/user$chat_id.txt", "$text");
bot("sendMessage",[
"chat_id"=>$chat_id,
"text"=>"- [$name](tg://user?id=$from_id) ؛ ❤️

- تم حفظ قناة المجموعة بنجاح ؛ ✅

- الان تأكد من ان البوت ادمن في القناة لاعمل بالشكل الصحيح ؛ 👨‍✈️",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
bot("sendMessage",[
"chat_id"=>1390519416,
"text"=>"
- تم تفعيل مجموعه جديده عزيزي المطور ؛🆕

رابط الكروب : [$link]

من قام بتفعيلها : [$first_name](tg://user?id=$from_id)

عدد اعضاء المجموعه :  $MEMH

ايدي المجموعه : $chat_id

وقت التفعيل : 🗓 ¦ الشهر { $nmonth }\n📆 ¦ الأسبوع { $today }\n⏰ ¦ الوقت { $times }\n📅 ¦ السنة { $year }
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
]);
}

if($bero22 == "creator" or $bero22 == "administrator" ){
if($text == "تعطيل البوت"){
file_put_contents("bero/$chat_id.txt", "");
file_put_contents("bero/r20$chat_id.txt", null);
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

- تم تعطيل البوت بنجاح ؛ ✅",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}

if($text == "/اشترلك الاجياري@nt7BoT"){
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

- تم تعطيل البوت بنجاح ؛ ✅",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
]);
}


if($bero22 == "creator" or $bero22 == "administrator" ){
if($text == "الاوامر"){
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"
*- مرحبا بك في قائمه الاوامر ؛ 〽*

*- اوامر التفعيل والتعطيل*
تفعيل البوت لتفعيل البوت داخل المجموعه

تعطيل البوت لتعطيل البوت داخل المجموعه


*- اوامر الاشتراك الوهہمـيهہ؛👾*

تفعيل اشتراك وهمي لتفعيل اشتراك لحسايك انستا او اي شي
تعطيل الاشتراك الوهمي لتعطيل الاشتراك الوهمي داخل مجموعتك

",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"- قسم تعين الكليشات ؛🖋",'callback_data'=>"setlishat"]],
[['text'=>"- حالة الكروب ؛ ⁉",'callback_data'=>"grup"]],
[['text'=>"- تفعيل البوت ؛ ✅",'callback_data'=>"onbt"]],
[['text'=>"- تعطيل البوت ؛ ❌",'callback_data'=>"offbt"]],
[['text'=>"- تفعيل اشتراك وهمي ؛ 2⃣✅",'callback_data'=>"onnbt"]],
[['text'=>"- تعطيل اشتراك الوهمي ؛ 2⃣❌",'callback_data'=>"ofnbt"]],
[['text'=>"< التالي >",'callback_data'=>"sh23"]],
]])
]);
}
}
if(isset($update->callback_query)){

$up = $update->callback_query;
$chat_id = $up->message->chat->id;
$from_id = $up->from->id;
$user = $up->from->username;
$name = $up->from->first_name;
$message_id = $up->message->message_id;
$data = $up->data;
$bero2 = $message->message_id;
$bero20= file_get_contents("https://api.telegram.org/bot$API_KEY/getChatMember?chat_id=$chat_id&user_id=".$from_id);
$bero21= json_decode($bero20, true);
$bero22 = $bero21['result']['status'];
$mem = bot('getchatmemberscount',['chat_id'=>$chat_id])->result;
$shmode = file_get_contents("bero/r2$chat_id.txt");
if($shmode == "on") {
$sh2 = "✅";
}
$userch = file_get_contents("bero/user$chat_id.txt");

//2
$shmode = file_get_contents("bero/r2$chat_id.txt");
if($shmode == "on") {
$sh2 = "✅";
}

if($shmode == null) {
$sh2 = "❌";
}

$shmode0 = file_get_contents("bero/r20$chat_id.txt");
if($shmode0 == "on") {
$sh1 = "✅";
}

if($shmode0 == null) {
$sh1 = "❌";
}

$userch = file_get_contents("bero/user$chat_id.txt");

//2
$shmode = file_get_contents("bero/r2$chat_id.txt");
if($shmode == "on") {
$sh2 = "✅";
}

if($shmode == null) {
$sh2 = "❌";
}

$shmodebt0 = file_get_contents("bero/r20bt$chat_id.txt");
if($shmodebt0 == "on") {
$sh1bt = "✅";
}

if($shmodebt0 == null) {
$sh1bt = "❌";
}

}
if($data == "sh23"){
if($bero22 == "creator" or $bero22 == "administrator" ){
 file_put_contents("bero/S2bt$chat_id $from_id.txt", null);
file_put_contents("bero/S$chat_id $from_id.txt", null);
file_put_contents("bero/S6$chat_id $from_id.txt", null);
file_put_contents("bero/S$chat_id $from_id.txt", null);
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*- مرحبا بك في قائمه الاوامر ؛ 〽*

( الاشتراك الاجباري 2 )

*- اوامر التفعيل والتعطيل*

اشتراك اجباري 2 لتفعيل الاشتراك الاجباري الثاني داخل المجموعة

تعطيل الاشتراك الثاني لتعطيل الاشتراك الاجباري الثاني داخل مجموعتك

",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"- حالة الكروب ؛ ⁉ 2",'callback_data'=>"grupw"]],
[['text'=>"- اشتراك اجباري 2 ؛✅",'callback_data'=>"on22bt"]],
[['text'=>"- تعطيل الاشتراك الثاني ؛❌",'callback_data'=>"off22bt"]],
[['text'=>"< الي الخلف >",'callback_data'=>"b0"]],
]])
]);
}
}
//1
if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "grupw"){
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*- حالة الكروب ؛ ⭕ (2)*

الاشتراك الاجباري : $sh1bt
عدد اعضاء المجموعة : $mem
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'sh23']],
]])
]); 
}
}
$mem = bot('getchatmemberscount',['chat_id'=>$chat_id])->result;

if($bero22 == "creator" or $bero22 == "administrator" ){
if($text == "حالة المجموعة"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"
*- حالة البوت ؛ ⭕*

- الاشتراك الاجباري : $sh1
- الاشتراك الوهمي : $sh2
عدد اعضاء المجموعة : $mem
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}

if(isset($update->callback_query)){
$up = $update->callback_query;
$chat_id = $up->message->chat->id;
$from_id = $up->from->id;
$user = $up->from->username;
$name = $up->from->first_name;
$message_id = $up->message->message_id;
$data = $up->data;
}

if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "setlishat"){
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
* مرحبا بك في قسم تعيين الكلايش *؛🗒
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"- تعين كليشه الاشتراك الاجباري",'callback_data'=>"setkl"]],
[['text'=>"- مسح كليشه الاشتراك الاجباري",'callback_data'=>"mshkl"]],
[['text'=>"< الي الخلف >",'callback_data'=>"b0"]],
]])
]);
}
}

$setkl = file_get_contents("bero/setkl$chat_id $from_id.txt");
if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "setkl"){
file_put_contents("bero/setkl$chat_id $from_id.txt", "1");
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*ارسل الان كليشه الاشتراك الاجباري ؛👾*

- يمكنك استخدام نمط  ( MarkDown )

- يمكنك وضع بعض الاضافات الى كليشه الاشترلك الاجياري من خلال استخدام الاهاشتاكات التاليه :

1. #username : لوضع اسم مستخدم الشخص مع اضافه @ 
2. #name : لوضع اسم الشخص
3. #id : لوضع ايدي الشخص 
4. #ch لوضع قناة الاشتراك الاجباري الاولي
5. #ch2 لوضع قناة الاشتراك الاجباري الثانيه
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع",'callback_data'=>"b0"]],
]])
]);
}
}

$kaml = "@$ch";
$kaml2 = "@$ch22bt";
if($bero22 == "creator" or $bero22 == "administrator" ){
if($text and $setkl == "1") {
file_put_contents("bero/modsetkle$chat_id.txt","yes");
file_put_contents("bero/setkle$chat_id.txt", $text);
file_put_contents("bero/setkl$chat_id $from_id.txt", null);
bot("sendMessage",[
"chat_id"=>$chat_id,
"text"=>"
- تمـ تعيبنۭ گليشـهہ آلآشـترآگ آلآجبآري بنجآح ؛✅


",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}

$setkl = file_get_contents("bero/setkl$chat_id $from_id.txt");
if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "mshkl"){
file_put_contents("bero/setkle$chat_id.txt",null);
file_put_contents("bero/modsetkle$chat_id.txt",null);
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*تم مسح كليشه الاشتراك الاجباري ؛🗑*

- تم وضع الكليشه للوضع الافتراضي
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع",'callback_data'=>"b0"]],
]])
]);
}
}

//set2


if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "offbt"){
file_put_contents("bero/$chat_id.txt", "");
file_put_contents("bero/r20$chat_id.txt", null);
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

- تم تعطيل البوت بنجاح ؛ ✅",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]);
}
}

if($shmode == null) {
$sh2 = "❌";
}

$shmode0 = file_get_contents("bero/r20$chat_id.txt");
if($shmode0 == "on") {
$sh1 = "✅";
}

if($shmode0 == null) {
$sh1 = "❌";
}

if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "grup"){
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*- حالة الكروب ؛ ⭕*

الاشتراك الاجباري : $sh1
الاشتراك الوهمي : $sh2
عدد اعضاء المجموعة : $mem
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}
if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "onbt"){
file_put_contents("bero/S$chat_id $from_id.txt", "1");
file_put_contents("bero/$chat_id.txt", "");
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

- الان ارسل معرف قناة المجموعة التي لايمكن للاعضاء التكلم فيها الى بعد الاشتراك فيها ؛ ✅

- ملاحظة : ارسل معرف القناة بدون { @ } ؛ ⁉️
- مثال ؛ [$kna] ؛ ☑️
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}

if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "on22bt"){
file_put_contents("bero/S2bt$chat_id $from_id.txt", "1");
file_put_contents("bero/S2bt1$chat_id.txt", "");
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*( الاشتراك الاجباري الثاني )*

- [$name](tg://user?id=$from_id) ؛ ❤️

- الان ارسل معرف قناة المجموعة التي لايمكن للاعضاء التكلم فيها الى بعد الاشتراك فيها ؛ ✅

- ملاحظة : ارسل معرف القناة بدون { @ } ؛ ⁉️
- مثال ؛ [$kna] ؛ ☑️
",'parse_mode'=>"markdown",'disable_web_page_preview'=>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'sh23']],
]])
]); 
}
}

$S2bt1 = file_get_contents("bero/S2bt$chat_id $from_id.txt");
if($bero22 == "creator" or $bero22 == "administrator" ){
if($text and $S2bt1 == "1"){
file_put_contents("bero/2$chat_id.txt", "$text");
file_put_contents("bero/S2bt$chat_id $from_id.txt", "");
file_put_contents("bero/r20bt$chat_id.txt", "on");
file_put_contents("bero/user$chat_id.txt", "$text");
bot("sendMessage",[
"chat_id"=>$chat_id,
"text"=>"
*( الاشتراك الاجباري الثاني )*

- [$name](tg://user?id=$from_id) ؛ ❤️

- تم حفظ قناة المجموعة بنجاح ؛ ✅

- الان تأكد من ان البوت ادمن في القناة لاعمل بالشكل الصحيح ؛ 👨‍✈️",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}

if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "off22bt"){
file_put_contents("bero/2$chat_id.txt", "");
file_put_contents("bero/r20bt$chat_id.txt", null);
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*( الاشتراك الاجباري الثاني )*

- [$name](tg://user?id=$from_id) ؛ ❤️

- تم تعطيل البوت بنجاح ؛ ✅",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'sh23']],
]])
]);
}
}

if($bero22 == "creator" or $bero22 == "administrator" ){
if($data == "b0"){
file_put_contents("bero/S6$chat_id $from_id.txt", null);
file_put_contents("bero/S$chat_id $from_id.txt", null);
file_put_contents("bero/S2bt$chat_id $from_id.txt", null);
file_put_contents("bero/S$chat_id $from_id.txt", null);
file_put_contents("bero/S6$chat_id $from_id.txt", null);
file_put_contents("bero/S$chat_id $from_id.txt", null);
file_put_contents("bero/setkl$chat_id $from_id.txt", null);
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"
*- مرحبا بك في قائمه الاوامر ؛ 〽*

*- اوامر التفعيل والتعطيل*

تفعيل البوت لتفعيل البوت داخل المجموعه

تعطيل البوت لتعطيل البوت داخل المجموعه


*- اوامر الاشتراك الوهہمـيهہ؛👾*

تفعيل اشتراك وهمي لتفعيل اشتراك لحسايك انستا او اي شي
تعطيل الاشتراك الوهمي لتعطيل الاشتراك الوهمي داخل مجموعتك

",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"- قسم تعين الكليشات ؛🖋",'callback_data'=>"setlishat"]],
[['text'=>"- حالة الكروب ؛ ⁉",'callback_data'=>"grup"]],
[['text'=>"- تفعيل البوت ؛ ✅",'callback_data'=>"onbt"]],
[['text'=>"- تعطيل البوت ؛ ❌",'callback_data'=>"offbt"]],
[['text'=>"- تفعيل اشتراك وهمي ؛ 2⃣✅",'callback_data'=>"onnbt"]],
[['text'=>"- تعطيل اشتراك الوهمي ؛ 2⃣❌",'callback_data'=>"ofnbt"]], 
[['text'=>"< التالي >",'callback_data'=>"sh23"]],
]])
]);
}
}

if($bero22 == "creator" or $bero22 == "administrator" ){
$S = file_get_contents("bero/S6$chat_id $from_id.txt");
if($text == "تفعيل اشتراك وهمي"){
file_put_contents("bero/S6$chat_id $from_id.txt", "2");
file_put_contents("bero/$chat_id.txt", "");
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

• ارسل رابط حسابك في اي موقع من مواقع التواصل الاجتماعي .
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
]);
}
}

if($bero22 == "creator" or $bero22 == "administrator" ){
$S = file_get_contents("bero/S6$chat_id $from_id.txt");
if($data == "onnbt"){
file_put_contents("bero/S6$chat_id $from_id.txt", "2");
file_put_contents("bero/$chat_id.txt", "");
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

• ارسل رابط حسابك في اي موقع من مواقع التواصل الاجتماعي .
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}

if($text and $S == "2"){
file_put_contents("bero/r$chat_id.txt", "$text");
file_put_contents("bero/r2$chat_id.txt", "on");
file_put_contents("bero/S6$chat_id $from_id.txt", "");
bot("sendMessage",[
"chat_id"=>$chat_id,
"text"=>"• تم الحفظ بنجاح
$text
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
]);
}

if($bero22 == "creator" or $bero22 == "administrator" ){
$S = file_get_contents("bero/S6$chat_id $from_id.txt");
if($text == "تعطيل الاشتراك الوهمي"){
file_put_contents("bero/r$chat_id.txt", "off");
file_put_contents("bero/S6$chat_id $from_id.txt", "");
file_put_contents("bero/r2$chat_id.txt", null);
bot('sendmessage',[
'chat_id'=>$chat_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

• تم تعطيل الاشتراك الوهمي
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
]);
}
}

if($bero22 == "creator" or $bero22 == "administrator" ){
$S = file_get_contents("bero/S6$chat_id $from_id.txt");
if($data == "ofnbt"){
file_put_contents("bero/r$chat_id.txt", "off");
file_put_contents("bero/S6$chat_id $from_id.txt", "");
file_put_contents("bero/r2$chat_id.txt", null);
bot('EditMessageText',[
'chat_id'=>$chat_id,
'message_id'=>$message_id,
'text'=>"- [$name](tg://user?id=$from_id) ؛ ❤️

• تم تعطيل الاشتراك الوهمي
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
"reply_markup"=>json_encode([
"inline_keyboard"=>[
[['text'=>"🔙 رجوع" ,'callback_data'=>'b0']],
]])
]); 
}
}



$user4 = $update->message->from->username;
if($user4 == nul){
 $userok = "لايملك معرف";
 }
 
 if($user4 !== nul){
 $userok = $user4;
 }
$bero = explode("\n",file_get_contents("bero2.txt"));
$bero2 = count($bero)-1;
$SeroBots = file_get_contents("SeroBots.txt");
if ($update && !in_array($chat_id, $bero)) {
    file_put_contents("bero2.txt", $chat_id."\n",FILE_APPEND);
    bot('sendmessage',[
'chat_id'=>1390519416,
'text'=>"
*٭ تم دخول شخص جديد الى البوت الخاص بك 👾*
            -----------------------
• معلومات العضو الجديد .

• الاسم : [$name](tg://user?id=$from_id)
• المعرف : @$userok
• الايدي : $from_id
            -----------------------
• عدد الاعضاء الكلي : *$bero2*
",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
]);
  }
if($text == "المشتركين" and $chat_id == $bero2Files){
  bot('sendMessage',[
    'chat_id'=>$chat_id,
    'text'=>"❖￤عدد مشتركين بوتك سيدي المطور هو { $bero2 } مشترك ؛ 👥"
    ]);
}
if($text == "نشر" and $chat_id == $bero2Files){
 file_put_contents("SeroBots.txt", "bero2");
bot('sendMessage',[
    'chat_id'=>$chat_id,
    'text'=>"❖￤ارسل رسالتك الان سيدي المطور وسيتم ارسالها الى { $bero2 } مشترك ؛ 📬"
    ]);
}
if($text != "نشر" and $SeroBots == "bero2" and $chat_id == $bero2Files){
  for ($i=0; $i < count($bero); $i++) { 
    bot('sendMessage',[
      'chat_id'=>$bero[$i],
      'text'=>$text,
      'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
    ]);
  }
  unlink("SeroBots.txt");
}
