MandrillComponent
=================

Mandrill Component for CakePHP 2.x

## 1. Install

Copy or git clone ```MandrillComponent.php``` to ```app/Controller/Component/```

## 2. Setup

### In a Controller:
    public $components = array(
        'Mandrill' => array('key' => 'YOUR_API_KEY'),
        );

## 3. Use

The Component automagically converts function calls to json API requests.

    //For Example:
    $this->Mandrill->usersInfo();    
    //Becomes a call to
    https://mandrillapp.com/api/1.0/users/info.json
    
to pass arguments:
    $this->Mandrill->messagesSend(array(
            'message' => array(
                'text' => 'Mandrill Mail',
                'html' => '<p>Test email from <strong>Mandrill API</strong></p>',
                "subject" => "Testing CakePHP Component Settings",
                "from_email" => "YOUE_EMAIL_HERE",
                "from_name" => "YOUR_NAME_HERE",
                "to" => array(
                        array(
                            "email" => "TEST_RECPT_EMAIL_HERE",
                            "name" => "TEST_RECPT_NAME_HERE",
                        ),
                    ),
            )
        )));
