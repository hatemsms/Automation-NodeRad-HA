# Automation-NodeRad-HA
This could be useful for people who are attempting to create an automation that is triggered by a particular time and date throughout the week or month. I'm just a user attempting to share what I couldn't find during my learning process; I'm not an expert but i am sure this could be a good start 
[{"id":"84551ced0f702723","type":"tab","label":"KidsRoom test","disabled":false,"info":"","env":[]},{"id":"13398a66b5cbe270","type":"comment","z":"84551ced0f702723","name":"KidsRoom Mode","info":"","x":160,"y":60,"wires":[],"icon":"node-red/alert.svg"},{"id":"5aec2422bb804438","type":"server-state-changed","z":"84551ced0f702723","name":"kids Occupancy","server":"75d5c52c.70a10c","version":6,"outputs":2,"exposeAsEntityConfig":"","entities":{"entity":["binary_sensor.kids_occupancy_occupancy"],"substring":[],"regex":[]},"outputInitially":false,"stateType":"str","ifState":"on","ifStateType":"str","ifStateOperator":"is","outputOnlyOnStateChange":true,"for":"0","forType":"num","forUnits":"minutes","ignorePrevStateNull":false,"ignorePrevStateUnknown":false,"ignorePrevStateUnavailable":false,"ignoreCurrentStateUnknown":false,"ignoreCurrentStateUnavailable":false,"outputProperties":[{"property":"payload","propertyType":"msg","value":"","valueType":"entityState"},{"property":"data","propertyType":"msg","value":"","valueType":"eventData"},{"property":"topic","propertyType":"msg","value":"","valueType":"triggerId"}],"x":160,"y":220,"wires":[["d7768238b9661ef9","bcfe5d456b28dbd3","93fc9654c06c7326"],["7bc28bd0c67509ba"]]},{"id":"e433982220ad89f4","type":"api-call-service","z":"84551ced0f702723","name":"TVon","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_on","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.kids_tv_socket_1"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_on","x":650,"y":100,"wires":[[]]},{"id":"1fd4dbde4ba037e9","type":"inject","z":"84551ced0f702723","name":"light on ","props":[{"p":"payload"},{"p":"topic","vt":"str"}],"repeat":"","crontab":"","once":false,"onceDelay":0.1,"topic":"on","payload":"","payloadType":"date","x":150,"y":460,"wires":[["7bc28bd0c67509ba"]]},{"id":"d7768238b9661ef9","type":"within-time-switch","z":"84551ced0f702723","name":"Morning Mode Tv Only","nameInt":"","positionConfig":"50c0ce2e29010da7","startTime":"sunriseStart","startTimeType":"pdsTime","startOffset":"190","startOffsetType":"num","startOffsetMultiplier":60000,"endTime":"sunsetStart","endTimeType":"pdsTime","endOffset":"-30","endOffsetType":"num","endOffsetMultiplier":60000,"timeRestrictions":0,"timeRestrictionsType":"none","timeDays":"*","timeOnlyOddDays":false,"timeOnlyEvenDays":false,"timeOnlyOddWeeks":false,"timeOnlyEvenWeeks":false,"timeMonths":"*","timedatestart":"","timedateend":"","propertyStart":"","propertyStartType":"none","propertyStartCompare":"true","propertyStartThreshold":"","propertyStartThresholdType":"num","startTimeAlt":"","startTimeAltType":"entered","startOffsetAlt":0,"startOffsetAltType":"none","startOffsetAltMultiplier":60000,"propertyEnd":"","propertyEndType":"none","propertyEndCompare":"true","propertyEndThreshold":"","propertyEndThresholdType":"num","endTimeAlt":"","endTimeAltType":"entered","endOffsetAlt":0,"endOffsetAltType":"none","endOffsetAltMultiplier":60000,"withinTimeValue":"true","withinTimeValueType":"msgInput","outOfTimeValue":"false","outOfTimeValueType":"msgInput","tsCompare":"0","x":460,"y":120,"wires":[["e433982220ad89f4"],[]]},{"id":"bcfe5d456b28dbd3","type":"within-time-switch","z":"84551ced0f702723","name":"Night Mode Till 22:00 PM","nameInt":"","positionConfig":"b2e3df80af0f37f4","startTime":"sunsetStart","startTimeType":"pdsTime","startOffset":"-30","startOffsetType":"num","startOffsetMultiplier":60000,"endTime":"22:00","endTimeType":"entered","endOffset":0,"endOffsetType":"none","endOffsetMultiplier":60000,"timeRestrictions":0,"timeRestrictionsType":"none","timeDays":"1,2,3,6,0","timeOnlyOddDays":false,"timeOnlyEvenDays":false,"timeOnlyOddWeeks":false,"timeOnlyEvenWeeks":false,"timeMonths":"*","timedatestart":"","timedateend":"","propertyStart":"","propertyStartType":"none","propertyStartCompare":"true","propertyStartThreshold":"","propertyStartThresholdType":"num","startTimeAlt":"","startTimeAltType":"entered","startOffsetAlt":0,"startOffsetAltType":"none","startOffsetAltMultiplier":60000,"propertyEnd":"","propertyEndType":"none","propertyEndCompare":"true","propertyEndThreshold":"","propertyEndThresholdType":"num","endTimeAlt":"","endTimeAltType":"entered","endOffsetAlt":0,"endOffsetAltType":"none","endOffsetAltMultiplier":60000,"withinTimeValue":"true","withinTimeValueType":"msgInput","outOfTimeValue":"false","outOfTimeValueType":"msgInput","tsCompare":"0","x":450,"y":200,"wires":[["4ac59e965f31daea"],[]]},{"id":"93fc9654c06c7326","type":"within-time-switch","z":"84551ced0f702723","name":"Meekends Mode TIll 23:59","nameInt":"","positionConfig":"bd25fdfbcdcdeb96","startTime":"sunsetStart","startTimeType":"pdsTime","startOffset":"-30","startOffsetType":"num","startOffsetMultiplier":60000,"endTime":"23:50","endTimeType":"entered","endOffset":0,"endOffsetType":"none","endOffsetMultiplier":60000,"timeRestrictions":0,"timeRestrictionsType":"none","timeDays":"4,5","timeOnlyOddDays":false,"timeOnlyEvenDays":false,"timeOnlyOddWeeks":false,"timeOnlyEvenWeeks":false,"timeMonths":"*","timedatestart":"","timedateend":"","propertyStart":"","propertyStartType":"none","propertyStartCompare":"true","propertyStartThreshold":"","propertyStartThresholdType":"num","startTimeAlt":"","startTimeAltType":"entered","startOffsetAlt":0,"startOffsetAltType":"none","startOffsetAltMultiplier":60000,"propertyEnd":"","propertyEndType":"none","propertyEndCompare":"true","propertyEndThreshold":"","propertyEndThresholdType":"num","endTimeAlt":"","endTimeAltType":"entered","endOffsetAlt":0,"endOffsetAltType":"none","endOffsetAltMultiplier":60000,"withinTimeValue":"true","withinTimeValueType":"msgInput","outOfTimeValue":"false","outOfTimeValueType":"msgInput","tsCompare":"0","x":460,"y":300,"wires":[["585d172b3204327c"],[]]},{"id":"4ac59e965f31daea","type":"api-call-service","z":"84551ced0f702723","name":"light on ","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_on","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.sonoff_1001fd29ba_2"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_on","x":660,"y":160,"wires":[["49a4eacbc5736884"]]},{"id":"49a4eacbc5736884","type":"api-call-service","z":"84551ced0f702723","name":"light on ","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_on","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.sonoff_1001fd29ba_1"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_on","x":800,"y":160,"wires":[["c87ef7e94ce3448c"]]},{"id":"c87ef7e94ce3448c","type":"api-call-service","z":"84551ced0f702723","name":"TVon","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_on","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.kids_tv_socket_1"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_on","x":930,"y":160,"wires":[[]]},{"id":"585d172b3204327c","type":"api-call-service","z":"84551ced0f702723","name":"light on ","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_on","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.sonoff_1001fd29ba_2"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_on","x":660,"y":340,"wires":[["3540899c10321cc3"]]},{"id":"3540899c10321cc3","type":"api-call-service","z":"84551ced0f702723","name":"light on ","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_on","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.sonoff_1001fd29ba_1"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_on","x":800,"y":340,"wires":[["fb04e8b9e44a0908"]]},{"id":"fb04e8b9e44a0908","type":"api-call-service","z":"84551ced0f702723","name":"TVon","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_on","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.kids_tv_socket_1"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_on","x":930,"y":340,"wires":[[]]},{"id":"7bc28bd0c67509ba","type":"api-call-service","z":"84551ced0f702723","name":"light off","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_off","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.sonoff_1001fd29ba_2"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_off","x":380,"y":480,"wires":[["b75fcefc41a42a6f"]]},{"id":"b75fcefc41a42a6f","type":"api-call-service","z":"84551ced0f702723","name":"light off","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_off","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.sonoff_1001fd29ba_1"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_off","x":520,"y":480,"wires":[["e43ea1281bbaa322"]]},{"id":"e43ea1281bbaa322","type":"api-call-service","z":"84551ced0f702723","name":"TV Off","server":"75d5c52c.70a10c","version":7,"debugenabled":false,"action":"switch.turn_off","floorId":[],"areaId":[],"deviceId":[],"entityId":["switch.kids_tv_socket_1"],"labelId":[],"data":"","dataType":"jsonata","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"switch","service":"turn_off","x":650,"y":480,"wires":[[]]},{"id":"75d5c52c.70a10c","type":"server","name":"Home Assistant","addon":true},{"id":"50c0ce2e29010da7","type":"position-config","name":"","isValide":"true","angleType":"deg","timeZoneOffset":99,"timeZoneDST":0,"stateTimeFormat":3,"stateDateFormat":12,"contextStore":""},{"id":"b2e3df80af0f37f4","type":"position-config","name":"","isValide":"true","angleType":"deg","timeZoneOffset":99,"timeZoneDST":0,"stateTimeFormat":3,"stateDateFormat":12,"contextStore":""},{"id":"bd25fdfbcdcdeb96","type":"position-config","name":"","isValide":"true","angleType":"deg","timeZoneOffset":99,"timeZoneDST":0,"stateTimeFormat":3,"stateDateFormat":12,"contextStore":""}]
