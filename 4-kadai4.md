```uml
@startuml
start
:weather = 天気予報;
if(weather = 0)then(true)
:快晴です;
elseif(weather = 1)then(true)
:曇りです;
elseif(weather = 2)then(true)
:雨です;
else(false)
:不明です;
endif
end
@enduml
```
