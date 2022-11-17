//Пересылает сообщения
    $getQuery = array
    (
        "chat_id" => TG_USER_ID,
        "text" => "Новое сообщение для бота",
        "parse_mode" => "html",
        "reply_to_message_id" => 47
    );

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . "/sendMessage?" . http_build_query($getQuery));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $resultQuery = curl_exec($ch);
    curl_close($ch);

    echo $resultQuery;


    //Удаляет сообщения
    /*$getQuery = array
    (
        "chat_id" => TG_USER_ID,
        "message_id" => 48
    );

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . "/deleteMessage?" . http_build_query($getQuery));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $resultQuery = curl_exec($ch);
    curl_close($ch);

    echo $resultQuery;*/

    //Сообщение с кнопками
    /*$getQuery = array
    (
        "chat_id" => TG_USER_ID,
        "text" => "Сообщение с кнопками",
        'reply_markup' => json_encode
        (
            array
            (
                'inline_keyboard' => array
                (
                    array
                    (
                        array
                        (
                            'text' => 'Button 1',
                            'callback_data' => 'test_2',
                        ),
                        array
                        (
                            'text' => 'Button 2',
                            'callback_data' => 'test_2',
                        ),
                    ),
                    array
                    (
                        array
                        (
                            'text' => 'Button 3',
                            'callback_data' => 'test_2',
                        ),
                        array
                        (
                            'text' => 'Button 4',
                            'callback_data' => 'test_2',
                        ),
                    ),
                ),
            )
        ),
    );

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . "/sendMessage?" . http_build_query($getQuery));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $resultQuery = curl_exec($ch);
    curl_close($ch);

    echo $resultQuery;*/


    //Сообщение с клавиатурой
    /*$getQuery = array
    (
        "chat_id" => TG_USER_ID,
        "text" => "Сообщение с кнопками",
        'reply_markup' => json_encode
        (
            array
            (
                'keyboard' => array
                (
                    array
                    (
                        array
                        (
                            'text' => 'Привет, как дела?',

                            'callback_data' => 'test_2',
                        ),
                        array
                        (
                            'text' => 'Чем занимаешься?',
                            'callback_data' => 'test_2',
                        ),
                    )
                ),
                'ont_time_keyboard' => TRUE,
                'resize_keyboard' => TRUE,
                $time = date('H:m:s'),
            )
        ),
    );

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . "/sendMessage?" . http_build_query($getQuery));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $resultQuery = curl_exec($ch);
    curl_close($ch);

    echo $resultQuery;*/


    //отправка картинки
    /*$arrayQuery = array
    (
        'chat_id' => 1250279205,
        'caption' => 'Проверка работы',
        'photo' => curl_file_create(__DIR__ . '/birdy_1.jpg')
    );

    $ch = curl_init('https://api.telegram.org/bot'. TG_TOKEN .'/sendPhoto');
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $arrayQuery);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $res = curl_exec($ch);
    curl_close($ch);*/


    //Вот здесь ниже у меня загвоздка - не могу зарегистрировать вебхук



    /*$getQuery = array
    (
        "url" => "https://prog-time.ru/tg_script/Moscow.php",
    );

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . "/setWebhook?" . http_build_query($getQuery));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $resultQuery = curl_exec($ch);
    curl_close($ch);
    
    echo $resultQuery;*/

    /*$data = file_get_contents('php://input');
    $data = json_decode($data, true);*/
/*
    function writeLogFile($string, $clear = false)
    {
        $log_file_name = __DIR__ . "/message.txt";
        if($clear == false)
        {
            $now = date("Y-m-d H:i:s");
            file_put_contents($log_file_name, $now . " " . print_r($string, true). "\r\n", FILE_APPEND);
        }
        else
        {
            $now = date("Y-m-d H:i:s");
            file_put_contents($log_file_name, '');
            file_put_contents($log_file_name, $now . " " . print_r($string, true). "\r\n", FILE_APPEND);
        }
    }

    $data = file_get_contents('php://input');
    $data = json_decode($data, true);
    writeLogFile($data, true);

    echo file_get_contents(__DIR__ . "/message.txt");*/

    /*if(!empty($data["message"]))
    {
        $file_id = $data["message"][1]["file_id"];
        writeLogFile($data, true);
        writeLogFile($data["message"][1]["file_id"]);
        /* массив с параметрами запроса *//*
        $getQuery = array(
            "file_id" => $file_id ,
        );
        $ch = curl_init("https://api.telegram.org/bot". TG_TOKEN ."/getFile?" . http_build_query($getQuery));
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
        curl_setopt($ch, CURLOPT_HEADER, false);

        $resultQuery = curl_exec($ch);
        curl_close($ch);

        writeLogFile($resultQuery, true);

        /* записываем ответ в формате PHP массива
        $arrDataResult = json_decode($resultQuery, true);

        /* записываем URL необходимого изображения
        $fileUrl = $arrDataResult["result"]["file_path"];

        /* формируем полный URL до файла
        $photoPathTG = "https://api.telegram.org/file/bot". TG_TOKEN ."/" . $fileUrl;

        /* забираем название файла
        $arrFilePath = explode("/", $fileUrl);
        $newFilerPath = __DIR__ . "/img/" . $arrFilePath[1];

        /* сохраняем файл на сервер
        file_put_contents($newFilerPath , file_get_contents($photoPathTG));
    }*/




    //сообщение, где кнопки находятся на клавиатуре
    /*$getQuery = array
    (
        "chat_id" => TG_USER_ID,
        "text" => "Сообщение",
        'reply_markup' => json_encode
        (
            array
            (
                'keyboard' => array
                (
                    array
                    (
                        array
                        (
                            'text' => 'Привет, как дела?',

                            'callback_data' => 'test_2',
                        ),
                        $time = date('H:m:s'),
                        array
                        (
                            'text' => 'Чем занимаешься?',
                            'callback_data' => 'test_2',
                        ),
                    )
                ),
                'ont_time_keyboard' => TRUE,
                'resize_keyboard' => TRUE,
                $time = date('H:m:s'),
            )
        ),
    );

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . "/sendMessage?" . http_build_query($getQuery));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $resultQuery = curl_exec($ch);
    curl_close($ch);

    echo $resultQuery;*/


    //еще одно сообщение с кнопками
    /*$getQuery = array
    (
        "chat_id" => TG_USER_ID,
        "text" => "Сообщение с кнопками",
        'reply_markup' => json_encode
        (
            array
            (
                'inline_keyboard' => array
                (
                    array
                    (
                        array
                        (
                            'text' => 'Button 1',
                            'callback_data' => 'test_2',
                        ),
                        array
                        (
                            'text' => 'Button 2',
                            'callback_data' => 'test_2',
                        ),
                    )
                ),
            )
        ),
    );

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . "/sendMessage?" . http_build_query($getQuery));
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $resultQuery = curl_exec($ch);
    curl_close($ch);

    echo $resultQuery;*/



    //отправка нескольких фотографий в одном сообщении
   /* $arrayQuery = array
    (
        'chat_id' => TG_USER_ID,
        'caption' => 'Проверка работы',
        'photo' => curl_file_create(__DIR__ . '/birdy_1.jpg', 'image.jpg', 'birdy_1.jpg'),
        'protect_content' => true,
    );

    //vardump($arrayQuery);

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . '/sendPhoto');
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $arrayQuery);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $res = curl_exec($ch);
    curl_close($ch);

    echo $res;*/



    //отправка нескольких картинок в виде альбома
/*
    $arrayQuery = array
    (
        'chat_id' => TG_USER_ID,
        'caption' => 'Проверка работы',
        'document' => curl_file_create(__DIR__ . '/birdy_1.jpg', 'image.jpg', 'birdy_1.jpg'),
    );

    //vardump($arrayQuery);

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . '/sendDocument');
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $arrayQuery);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $res = curl_exec($ch);
    curl_close($ch);

    echo $res;*/



    //пересылка картинки
    /*$arrayQuery = array
    (
        'chat_id' => TG_USER_ID,
        'caption' => 'Проверка работы',
        'document' => "BQACAgIAAxkDAANmY3YT9wUKTlgsh65mrXK6Elx2_tQAArUdAAKm6LBLY2H1Y9yjl5grBA",
    );

    //vardump($arrayQuery);

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . '/sendDocument');
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $arrayQuery);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $res = curl_exec($ch);
    curl_close($ch);

    echo $res;*/


    /*$arrayQuery = [
        'chat_id' => TG_USER_ID,
        'media' => json_encode([
            ['type' => 'photo', 'media' => 'attach://birdy_1'],
            ['type' => 'photo', 'media' => 'attach://live_aid'],
        ]),
        'birdy_1' => new CURLFile(__DIR__ . '/birdy_1.jpg'),
        'live_aid' => new CURLFile(__DIR__ . '/live_aid.jpg'),
    ];

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . '/sendMediaGroup');
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $arrayQuery);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $res = curl_exec($ch);
    curl_close($ch);

    echo $res;*/



    /*$arrayQuery = [
        'chat_id' => TG_USER_ID,
        'media' => json_encode([
            ['type' => 'document', 'media' => 'attach://birdy_1'],
            ['type' => 'document', 'media' => 'attach://live_aid'],
        ]),
        'birdy_1' => new CURLFile(__DIR__ . '/birdy_1.jpg'),
        'live_aid' => new CURLFile(__DIR__ . '/live_aid.jpg'),
    ];

    $ch = curl_init("https://api.telegram.org/bot" . TG_TOKEN . '/sendMediaGroup');
    curl_setopt($ch, CURLOPT_POST, 1);
    curl_setopt($ch, CURLOPT_POSTFIELDS, $arrayQuery);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($ch, CURLOPT_HEADER, false);

    $res = curl_exec($ch);
    curl_close($ch);

    echo $res;*/


    //мои попытки создать интерфейс(неудачно)


    /* для отправки текстовых сообщений */
    /*function TG_sendMessage($getQuery) {
        $ch = curl_init("https://api.telegram.org/bot". TG_TOKEN ."/sendMessage?" . http_build_query($getQuery));
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
        curl_setopt($ch, CURLOPT_HEADER, false);
        $res = curl_exec($ch);
        curl_close($ch);

        return $res;
    }*/

    /* для отправки изображений */
    /*function TG_sendPhoto($arrayQuery) {
        $ch = curl_init('https://api.telegram.org/bot'. TG_TOKEN .'/sendPhoto');
        curl_setopt($ch, CURLOPT_POST, 1);
        curl_setopt($ch, CURLOPT_POSTFIELDS, $arrayQuery);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
        curl_setopt($ch, CURLOPT_HEADER, false);
        $res = curl_exec($ch);
        curl_close($ch);

        return $res;
    }*/

    /* для получения данных о файле *//*
    function TG_getFile($arrayQuery) {
        $ch = curl_init("https://api.telegram.org/bot". TG_TOKEN ."/getFile?" . http_build_query($arrayQuery));
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
        curl_setopt($ch, CURLOPT_HEADER, false);
        $res = curl_exec($ch);
        curl_close($ch);

        return $res;
    }*/
