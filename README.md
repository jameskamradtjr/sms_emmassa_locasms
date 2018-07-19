# sms_emmassa_locasms
 
   Como enviar enviar sms em massa utilizando o WebService LocaSMS
   
   Site para criar sua conta: http://locasms.com.br/


                   <?php

                    $login_locasms = '';
                    $senha_locasms = '';
                    $mensagem = '';
                    $numeros_locasms = '';//separe por virgula os numeros
        
                   
                    $Url = "http://209.133.205.2/painel/api.ashx";
                    #------------------[Envio dos dados]-----------------------------------
                    $sessao_curl = curl_init();
                    curl_setopt($sessao_curl, CURLOPT_URL, $Url);
                    curl_setopt($sessao_curl, CURLOPT_RETURNTRANSFER, 1);
                    curl_setopt($sessao_curl, CURLOPT_POST, 1);
                    curl_setopt($sessao_curl,CURLOPT_POSTFIELDS,"action=sendsms&lgn=$login_locasms&pwd=$senha_locasms&msg=$mensagem&numbers=$numeros_locasms");
                    $resultado = curl_exec($sessao_curl);
                    curl_close($sessao_curl);
                   

                    echo $resultado;

                   