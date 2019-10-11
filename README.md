# Introduction

This package seeks to help php developers implement the various Mpesa APIs without much hustle. It is based on the REST API whose documentation is available on https://developer.safaricom.co.ke.

#  Installation using composer
composer require wasksofts/mpesa --dev

#  example of configuration

require_once('vendor/autoload.php');

  use Wasksofts\Mpesa\Mpesa;

    $mpesa  = new Mpesa();
    $mpesa->config('consumer_key', '');
    $mpesa->config('consumer_secret', '');
    $mpesa->config('pass_key', '');
    $mpesa->config('initiator_name', '');
    $mpesa->config('initiator_pass', '');
    $mpesa->config('shortcode', '174379');
    $mpesa->config('shortcode1', '');
    $mpesa->config('shortcode2', '');
    $mpesa->config('callback_url', 'https://example.com/callback_url.php');
    $mpesa->config('confirmation_url', 'https://example.com/confirmation_url.php');
    $mpesa->config('validation_url', 'https://example.com/validation_url.php');
    $mpesa->config('result_url', 'https://example.com/result_url.php');
    $mpesa->config('timeout_url', 'https://example.com/timeout_url.php');
    $mpesa->config('env', 'sandbox');
    
    echo " Token : " . $mpesa->oauth_token();
    echo $mpesa->STKPushQuery('ws_CO_DMZ_297481201_09042019174418021');
    print_r($mpesa->STKPushSimulation('1','254708374149','pay now','test'));
    print_r( $mpesa->register_url()); 
    print_r($mpesa->c2b('10', '254708374149', 'account'));
    print_r($mpesa->b2c('2', 'BusinessPayment', '254708374149', 'payment')); //refund
    print_r($mpesa->b2b('10000','BusinessPayBill','60000','4','4','paytest','cool'));
    print_r($mpesa->accountbalance('600443','4','remarks'));
    print_r( $mpesa->reversal('2','254708374149','1','NCR7S1UXBT','PAY NOW VIA WASKSOFT'));
    print_r($mpesa->transaction_status('NCR7S1UXBT','254708374149','4','apitest'));
    
    //get responses
    echo $mpesa->getResponseData();
    
    
