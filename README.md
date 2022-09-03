ob_start();
$API_KEY = "2140104762:AAFtnov0K4I6WRQgRxUWgX1NJzbjIdol4dg";
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

  
if(isset($update->callback_query)){

$up = $update->callback_query;
$chat_id = $up->message->chat->id;
$from_id = $up->from->id;
$user = $up->from->username;
$name = $up->from->first_name;
$message_id = $up->message->message_id;
$data = $up->data;
}



$mode= file_get_contents("$from_id mode.txt");
if($text =="/start" ){
	$m3na= json_decode(file_get_contents("http://sero2link.ml/API/V1/Coin.php?m=IQD&t=USD&sr=100"),true);
	
bot('sendMessage',[
    'chat_id'=>$chat_id,
    'text'=>"
- اهلا بك عزيزي ، ([$name](tg://user?id=$from_id)) في بوت اسعار العملات 👋

- يمكنك معرفه اسعار العملات في البوت بسهولة ؛ ✅



",
'parse_mode'=>"MarkDown",
'disable_web_page_preview' =>true,
'reply_to_message_id'=>$message_id,
'reply_markup'=>json_encode([ 
      'inline_keyboard'=>[
[['text'=>'بدء استخدام البوت' ,'callback_data'=>"start"]],
]
])
    ]);
}


if($data == "start"){
bot('EditMessageText',[
    "chat_id"=>$chat_id,
    "message_id"=>$message_id,
"text"=>"
ا
",
"disable_web_page_preview"=>true,
'parse_mode'=>"markdown",
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>'دينار عراقي الي دولار امريكي' ,'callback_data'=>"iqtoen"],['text'=>'دولار امريكي الي دينار عراقي' ,'callback_data'=>"entoiq"]],
[['text'=>'دينار عراقي الي يورو اوروبي' ,'callback_data'=>"iqtoer"],['text'=>'يورو اوروبي الي دينار عراقي' ,'callback_data'=>"ertoiq"]],
]
])
]);
}

if($data == "iqtoen"){
	$m3na= json_decode(file_get_contents("http://sero2link.ml/API/V1/Coin.php?m=IQD&t=USD&sr=100"),true);
bot('EditMessageText',[
    "chat_id"=>$chat_id,
    "message_id"=>$message_id,
"text"=>"
- دينار عراقي مقابل دينار عراقي 

$m3na
",
"disable_web_page_preview"=>true,
'parse_mode'=>"markdown",
]);

}



if($data == "entoiq"){
	$m3na= json_decode(file_get_contents("http://sero2link.ml/API/V1/Coin.php?m=USD&t=IQD&sr=100"),true);
bot('EditMessageText',[
    "chat_id"=>$chat_id,
    "message_id"=>$message_id,
"text"=>"
- دولار امريكي مقابل دينار عراقي

$m3na
",
"disable_web_page_preview"=>true,
'parse_mode'=>"markdown",
]);

}

if($data == "iqtoer"){
	$m3na= json_decode(file_get_contents("http://sero2link.ml/API/V1/Coin.php?m=IQD&t=EUR&sr=100"),true);
bot('EditMessageText',[
    "chat_id"=>$chat_id,
    "message_id"=>$message_id,
"text"=>"
- دينار عراقي مقابل يورو اوروبي

$m3na
",
"disable_web_page_preview"=>true,
'parse_mode'=>"markdown",
]);

}

if($data == "ertoiq"){
	$m3na= json_decode(file_get_contents("http://sero2link.ml/API/V1/Coin.php?m=IQD&t=EUR&sr=100"),true);
bot('EditMessageText',[
    "chat_id"=>$chat_id,
    "message_id"=>$message_id,
"text"=>"
- يورو اوروبي مقابل دينار عراقي

$m3na
",
"disable_web_page_preview"=>true,
'parse_mode'=>"markdown",
]);
}
