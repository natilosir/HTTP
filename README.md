# http
function http request POST, GET

## required

- PHP >= 5.4
- Composer
- You can define the default address in line 2 of the http.php file
```bash
define('api','https://natilos.ir/');
```
# install

```bash
git clone https://github.com/natilosir/http/
```
<br><br>

## POST Method

- By default, requests are made with post method
```bash
$data_received = [
    'chat_id'    => $chat_id,
    'text'       => $text,
    'parse_mode' => "HTML",

];

return http('sendMessage', $data_received); // return OBJ
```

## GET method
```bash
$data_received = [
    'chat_id'    => $chat_id,
    'text'       => $text,
    'parse_mode' => "HTML",

];

return http('sendMessage', $data_received, 'get'); // return OBJ
```

- Send requests in an array
```bash
$data_received = [
    'chat_id'    => $chat_id,
    'text'       => $text,
    'parse_mode' => "HTML",

];

if ($reply_markup) {
    $data_received['reply_markup'] = $reply_markup;
}

if ($reply_to_message_id) {
  $data_received['reply_to_message_id'] = $reply_to_message_id;
}

  return http('sendMessage', $data_received, 'get');
    
```

