int LED = 9;  
    int BUZZER = 10;   
    int ALCOHOL_sensor = 3;// MQ-3 SENSOR  
    int ALCOHOL_detected;  
    void setup()  
    {  
     Serial.begin(9600);  
     pinMode(LED, OUTPUT);  
     pinMode(BUZZER, OUTPUT);  
     pinMode(ALCOHOL_sensor, INPUT);  
    }  
    void loop()  
    {  
      ALCOHOL_detected = digitalRead(ALCOHOL_sensor);  
      Serial.println(ALCOHOL_detected);  
     if (ALCOHOL_detected == true)  
     {
       digitalWrite(LED, HIGH);  
       digitalWrite(BUZZER, HIGH); 
       Serial.println("ALCOHOL detected...");  
     }  
     else  
     {  
       digitalWrite(LED, LOW);  
       digitalWrite(BUZZER, LOW);  
       Serial.println("No ALCOHOL detected.");  
     }  
    }
