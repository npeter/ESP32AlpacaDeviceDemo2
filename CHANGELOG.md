# Changelog ESP32AlpacaDevicesDemo2

## 0.0.0 2025-09-06 created / based on ESP32AlpacaDevicesDemo2

## 1.0.0 2025-09-08 
1. main.cpp VERSION 1.0.0


## Open/ongoing Topics
1. Test DeviceState with NINA 3.2 Beta 8
    
    ASCOM Device State: For drivers that implement the new ASCOM 7 Device State the application will now use the state when possible instead of polling individual fields



### Investigation Test with NINA 3.3 Beta 8

Status 2025-09-08
1. SWITCH: NOK - Zyklisch getswitchname 0 /getswitchvalue 0, ... , getswitchname 3 /getswitchvalue 3
    PUT connected True -> OK
    GET connected -> true OK
    GET interfaceversion -> 3 OK
    GET devicestate -> switchvalues... but not switchname?
    -> devicestate not called

2. OBSERVING_CONDITIONS: 
    PUT connected True -> OK
    GET connected -> true OK
    GET interfaceversion -> 2 OK
    GET devicestate ->  ... OK
    GET description -> ... OK
    GET averageperiod -> 0.0000 OK
    GET driverinfo -> ... OK
    GET devicestate -> ... OK
    GET driverversion -> ... OK
    GET rainrate -> ... OK
    GET devicestate -> ... OK
    NINA: Error Object reference not set to an instance of an object
    ... no put connection false
    -> Why rainrate ... missed in devicestate

3. FOCUSER
    PUT connected True -> OK
    GET connected -> true OK
    GET interfaceversion -> 4 OK
    GET devicestate -> ... tempcompavailable missed NOK
    ...
    cyclic: 
    GET devicestate
    GET tempcomp available -> missed
    GET connected

4. Cover Calibrator
    PUT connected True -> OK
    GET connected -> true OK
    GET interfaceversion -> 2 OK
    GET devicestate -> Brightness, CalibratorState, CoverState OK
    cyclic:
    GET devicestate
    GET calibratorstate -> WHY
    GET calibratorstate -> WHY
    GET connected
    






