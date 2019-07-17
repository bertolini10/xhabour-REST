LOCAL cRet := ""
LOCAL oUrl
LOCAL oWebService
LOCAL nTimeOut     := 0

cURL := "http://localhost:8880/rest/move_source_destination/call"
cParam :=' {" token ": "QRxr9mcHBBy8NIY9opYZv9MhgLaw4cwg7Dyf4wKhcwaIRbThXMw3jffDd4l468cp"," atoken ": "8ab267c5347ab6f386882ae4685fd542",  "move_source_destination": [  { "sequence_id": 3,"sequence_reference_id": 1,    "floor_id_source": "ANDAR_2","position_id_source": "POS_A","floor_id_destination": "ANDAR_3","position_id_destination": "POS_B"},{"sequence_id": 4,"floor_id_source": "ANDAR_5","position_id_source": "POS_A","floor_id_destination": "ANDAR_2","position_id_destination": "POS_B"}]} '

oUrl := tURLSSL():New( cUrl )
oWebService := TipClientSSLHTTP():New( oUrl,.t.)

if nTimeOut=0
   oWebService:nConnTimeout := 30000
else
   if nTimeOut > 100000
      nTimeOut := 100000
   endif
   oWebService:nConnTimeout := nTimeOut
endif

oWebService:hFields['Content-Type'] := "application/json"
oWebService:hFields['SOAPAction']   := "POST"
oWebService:cConnetion:='Keep-Alive'
oWebService:Open()
oWebService:Post(cParam)

cRet := oWebService:ReadAll()

oWebService:close() 

mens(cRet)  
