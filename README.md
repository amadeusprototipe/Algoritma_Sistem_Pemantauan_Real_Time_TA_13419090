[
    {
        "id": "c1cfd9835acb2e31",
        "type": "tab",
        "label": "Flow 1",
        "disabled": false,
        "info": "",
        "env": []
    },
    {
        "id": "a458855f3d9c6aa7",
        "type": "ui_switch",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Status On/Off",
        "tooltip": "",
        "group": "7a1198fbe6345632",
        "order": 1,
        "width": 0,
        "height": 0,
        "passthru": true,
        "decouple": "false",
        "topic": "Run",
        "topicType": "str",
        "style": "",
        "onvalue": "true",
        "onvalueType": "bool",
        "onicon": "",
        "oncolor": "",
        "offvalue": "false",
        "offvalueType": "bool",
        "officon": "",
        "offcolor": "",
        "animate": true,
        "className": "",
        "x": 280,
        "y": 300,
        "wires": [
            [
                "35fa073afb73f653",
                "2e1945c878e2ae0d",
                "922ac6c927e25815"
            ]
        ]
    },
    {
        "id": "f2b993cd0fc78993",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "Run",
                "fromt": "str",
                "to": "RUNNING",
                "tot": "str"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "Idle",
                "fromt": "str",
                "to": "IDLE",
                "tot": "str"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "Downtime",
                "fromt": "str",
                "to": "DOWNTIME",
                "tot": "str"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "Breakdown",
                "fromt": "str",
                "to": "BREAKDOWN",
                "tot": "str"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "reset",
                "fromt": "str",
                "to": "IDLE",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 1020,
        "y": 180,
        "wires": [
            [
                "bb9c88a56c9f8c9d",
                "bbcc37d1deb051ce"
            ]
        ]
    },
    {
        "id": "bb9c88a56c9f8c9d",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "7a1198fbe6345632",
        "order": 4,
        "width": 6,
        "height": "1",
        "name": "",
        "label": "Status",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1370,
        "y": 180,
        "wires": []
    },
    {
        "id": "bc7d4eb37659bdf7",
        "type": "ui_clock",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "254ff0e8700612df",
        "order": 1,
        "width": 4,
        "height": 4,
        "x": 990,
        "y": 40,
        "wires": []
    },
    {
        "id": "9eaa9703cee20c9d",
        "type": "inject",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "props": [
            {
                "p": "payload"
            },
            {
                "p": "topic",
                "vt": "str"
            }
        ],
        "repeat": "1",
        "crontab": "",
        "once": false,
        "onceDelay": 0.1,
        "topic": "",
        "payload": "",
        "payloadType": "date",
        "x": 790,
        "y": 60,
        "wires": [
            [
                "bc7d4eb37659bdf7",
                "3287ed89fa844795"
            ]
        ]
    },
    {
        "id": "8881532c513b7f05",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "254ff0e8700612df",
        "order": 2,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1230,
        "y": 80,
        "wires": []
    },
    {
        "id": "3287ed89fa844795",
        "type": "date-converter",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "topic": "",
        "input": "",
        "inputType": "msg",
        "inTz": "Asia/Jakarta",
        "adjAmount": 0,
        "adjType": "days",
        "adjDir": "add",
        "format": "DD/MM/YYYY HH:mm:ss",
        "locale": "en-US",
        "output": "",
        "outputType": "msg",
        "outTz": "Asia/Jakarta",
        "x": 1040,
        "y": 80,
        "wires": [
            [
                "8881532c513b7f05"
            ],
            []
        ]
    },
    {
        "id": "3a0f50f82e6a8652",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "29986c92d065db26",
        "order": 1,
        "width": 3,
        "height": 1,
        "name": "",
        "label": "Running Time",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1400,
        "y": 320,
        "wires": []
    },
    {
        "id": "f2698f2ac877b1d2",
        "type": "debug",
        "z": "c1cfd9835acb2e31",
        "name": "debug 3",
        "active": false,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "false",
        "statusVal": "",
        "statusType": "auto",
        "x": 1800,
        "y": 300,
        "wires": []
    },
    {
        "id": "4c79b5df5554c69f",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "80e2142f0aa4abd6",
        "order": 2,
        "width": "3",
        "height": "1",
        "name": "",
        "label": "Input (Pcs) ",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1050,
        "y": 640,
        "wires": []
    },
    {
        "id": "7b1a725d05bcf5ef",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "80e2142f0aa4abd6",
        "order": 7,
        "width": "3",
        "height": 1,
        "name": "",
        "label": "Output (CTN) ",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1520,
        "y": 880,
        "wires": []
    },
    {
        "id": "a0e5a66102b1fddb",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "80e2142f0aa4abd6",
        "order": 4,
        "width": 3,
        "height": 1,
        "name": "",
        "label": "Output (Pcs) ",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1550,
        "y": 940,
        "wires": []
    },
    {
        "id": "7d420ea837bef32c",
        "type": "ui_dropdown",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Pilih produk yang diproduksi !",
        "tooltip": "",
        "place": "Select option",
        "group": "3323f7416b9a5747",
        "order": 1,
        "width": 0,
        "height": 0,
        "passthru": true,
        "multiple": false,
        "options": [
            {
                "label": "",
                "value": "Choc Rocks Bar Choco Nut 65 mL @ 40 Pc",
                "type": "str"
            },
            {
                "label": "",
                "value": "Choc Rocks Bar Vanilla Nut 65 mL @40 Pc",
                "type": "str"
            },
            {
                "label": "",
                "value": "Choc Rocks Bar Red Velvet 65 mL @40 Pc",
                "type": "str"
            },
            {
                "label": "",
                "value": "Kul-Kul Igloo Chocolate @ 40 Pc",
                "type": "str"
            },
            {
                "label": "",
                "value": "Kul-Kul Igloo Vanilla @ 40 Pc",
                "type": "str"
            },
            {
                "label": "",
                "value": "Kul kul Igloo Choco Flakes 50 ml",
                "type": "str"
            },
            {
                "label": "",
                "value": "Kul Kul Fruity Blueberry",
                "type": "str"
            },
            {
                "label": "",
                "value": "Kul Kul Fruity Grape",
                "type": "str"
            }
        ],
        "payload": "",
        "topic": "pilproduk",
        "topicType": "str",
        "className": "",
        "x": 480,
        "y": 1240,
        "wires": [
            [
                "e72dd0e4a4d1101d"
            ]
        ]
    },
    {
        "id": "da35361a30e3660a",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "e34bc21bc9269937",
        "order": 2,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Produk :",
        "format": "{{msg.payload}}",
        "layout": "row-spread",
        "className": "",
        "x": 1460,
        "y": 1240,
        "wires": []
    },
    {
        "id": "85b3451a0d37fdc0",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "e34bc21bc9269937",
        "order": 3,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Target :",
        "format": "{{msg.payload}}",
        "layout": "row-spread",
        "className": "",
        "x": 1460,
        "y": 1280,
        "wires": []
    },
    {
        "id": "fc61a4586f6514ec",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "e34bc21bc9269937",
        "order": 4,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Waktu :",
        "format": "{{msg.payload}}",
        "layout": "row-spread",
        "className": "",
        "x": 1460,
        "y": 1420,
        "wires": []
    },
    {
        "id": "cdb1cfc3cd5edf16",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "e34bc21bc9269937",
        "order": 5,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Speed :",
        "format": "{{msg.payload}}",
        "layout": "row-spread",
        "className": "",
        "x": 2160,
        "y": 1400,
        "wires": []
    },
    {
        "id": "d42094b3c7d20015",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var counter1 = flow.get(\"counter1\") || 0;\nvar counterin1 = flow.get(\"counterin1\") || 0;\n\nif (msg.topic == \"reset\") {\n    counter1 = 0;\n    counterin1 = 0;\n} else if (msg.topic === \"input\") {\n    counter1 ++;\n} else if (msg.topic === \"inmanual\") {\n    counterin1 = msg.payload;\n};\n\nflow.set(\"counter1\", counter1);\nflow.set(\"counterin1\", counterin1);\n\nvar counterr1 = counter1 * 8 + counterin1;\n\nmsg.payload = counterr1;\n\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 870,
        "y": 640,
        "wires": [
            [
                "4c79b5df5554c69f",
                "4c4bc915b7a526e3"
            ]
        ]
    },
    {
        "id": "1a72122db03bc221",
        "type": "ui_button",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "aa0ad3153fa65903",
        "order": 2,
        "width": "2",
        "height": 1,
        "passthru": true,
        "label": "Sensor Input",
        "tooltip": "",
        "color": "",
        "bgcolor": "green",
        "className": "",
        "icon": "",
        "payload": "true",
        "payloadType": "bool",
        "topic": "input",
        "topicType": "str",
        "x": 450,
        "y": 720,
        "wires": [
            [
                "d42094b3c7d20015",
                "37c96ff11d59f39d",
                "a3371de42cb7b187",
                "c50fa9b4dab7f2c1",
                "2f71695934bb22e4"
            ]
        ]
    },
    {
        "id": "a7c3645ae6bb1a82",
        "type": "ui_button",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "aa0ad3153fa65903",
        "order": 5,
        "width": 4,
        "height": 1,
        "passthru": true,
        "label": "Reset",
        "tooltip": "",
        "color": "",
        "bgcolor": "gray",
        "className": "",
        "icon": "autorenew",
        "payload": "true",
        "payloadType": "bool",
        "topic": "reset",
        "topicType": "str",
        "x": 250,
        "y": 780,
        "wires": [
            [
                "563e17a402b9203c",
                "157d527fecce6420",
                "a7dfc66917643b04"
            ]
        ]
    },
    {
        "id": "9dfbb40fff24bf83",
        "type": "ui_button",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "aa0ad3153fa65903",
        "order": 3,
        "width": "2",
        "height": 1,
        "passthru": true,
        "label": "Sensor Output",
        "tooltip": "",
        "color": "",
        "bgcolor": "orange",
        "className": "",
        "icon": "",
        "payload": "true",
        "payloadType": "bool",
        "topic": "output",
        "topicType": "str",
        "x": 460,
        "y": 880,
        "wires": [
            [
                "00422132d69f71e2",
                "37c96ff11d59f39d",
                "2db6fe2e212b2458",
                "c50fa9b4dab7f2c1",
                "2f71695934bb22e4",
                "89ba432355685d81"
            ]
        ]
    },
    {
        "id": "00422132d69f71e2",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var counter2 = flow.get(\"counter2\") || 0;\nvar counterout3 = flow.get(\"counterout3\") || 0;\n\nif (msg.topic == \"reset\") {\n    counter2 = 0;\n    counterout3 = 0;\n} else if (msg.topic == \"output\") {\n    counter2++\n} else if (msg.topic === \"outmanual2\") {\n    counterout3 = msg.payload;\n};\n\nflow.set(\"counter2\", counter2);\nflow.set(\"counterout3\", counterout3);\n\nvar counterr2 = counter2 * 20 + counterout3;\n\nmsg.payload = counterr2;\n\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 940,
        "wires": [
            [
                "a0e5a66102b1fddb",
                "89d5229bac3a4815",
                "4994b08e85968849"
            ]
        ]
    },
    {
        "id": "37c96ff11d59f39d",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var counter3 = flow.get(\"counter3\") || 0;\nvar counter4 = flow.get(\"counter4\") || 0;\nvar counterin2 = flow.get(\"counterin2\") || 0;\nvar counterout1 = flow.get(\"counterout1\") || 0;\n\nif (msg.topic == \"reset\") {\n    counter3 = 0;\n    counter4 = 0;\n    counterin2 = 0;\n    counterout1 = 0;\n} else if (msg.topic == \"input\") {\n    counter3++\n} else if (msg.topic == \"output\") {\n    counter4++\n} else if (msg.topic === \"inmanual4\") {\n    counterin2 = msg.payload;\n} else if (msg.topic === \"outmanual\") {\n    counterout1 = msg.payload;\n};\n\nflow.set(\"counter3\", counter3);\nflow.set(\"counter4\", counter4);\nflow.set(\"counterin2\", counterin2);\nflow.set(\"counterout1\", counterout1);\n\nvar counterr3 = counter3 * 8 + counterin2;\nvar counterr4 = counter4 * 20 + counterout1;\nvar losses = counterr3 - counterr4;\n\nmsg.payload = losses;\n\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 870,
        "y": 720,
        "wires": [
            [
                "dcb641dc962e05b5",
                "8ac7dba5b9f0d770"
            ]
        ]
    },
    {
        "id": "dcb641dc962e05b5",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "80e2142f0aa4abd6",
        "order": 5,
        "width": "3",
        "height": 1,
        "name": "",
        "label": "Losses (Pcs)",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1050,
        "y": 720,
        "wires": []
    },
    {
        "id": "2db6fe2e212b2458",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var counter5 = flow.get(\"counter5\") || 0;\nvar outputctn = flow.get(\"outputctn\") || 0;\n\nif (msg.topic == \"reset\") {\n    counter5 = 0;\n    outputctn = 0;\n} else if (msg.topic == \"output\") {\n    counter5++;\n} else if (msg.topic === \"outmanualctn\") {\n    outputctn = msg.payload;\n};\n\nflow.set(\"counter5\", counter5);\nflow.set(\"outputctn\", outputctn);\n\nvar countoutputctn = counter5 / 2 + outputctn;\nmsg.payload = Math.floor(countoutputctn);\n\nreturn msg;\n",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 880,
        "wires": [
            [
                "7b1a725d05bcf5ef",
                "60391e289dd05392"
            ]
        ]
    },
    {
        "id": "b3ab881a3276fac1",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var value1 = flow.get(\"value1\");\nvar value2 = flow.get(\"value2\");\nvar value3 = flow.get(\"value3\");\n\nif (msg.topic === \"tarprod\") {\n    value1 = msg.payload;\n}\nelse if (msg.topic === \"tarjam\") {\n    value2 = msg.payload;\n    var speed = value1 / value2;\n    msg.payload = Math.ceil(speed) + \" \" + \"Pcs/jam\";\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    value1 = 0;\n    value2 = 0;\n    value3 = 0;\n    msg.payload = 0;\n    node.send(msg);\n}\nflow.set(\"value1\", value1);\nflow.set(\"value2\", value2);",
        "outputs": 1,
        "noerr": 0,
        "x": 1950,
        "y": 1360,
        "wires": [
            [
                "cdb1cfc3cd5edf16",
                "7463ae45b581d220"
            ]
        ]
    },
    {
        "id": "1b09358a5b6e4bd8",
        "type": "ui_switch",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Status Downtime",
        "tooltip": "",
        "group": "7a1198fbe6345632",
        "order": 2,
        "width": 0,
        "height": 0,
        "passthru": true,
        "decouple": "false",
        "topic": "DT",
        "topicType": "str",
        "style": "",
        "onvalue": "true",
        "onvalueType": "bool",
        "onicon": "",
        "oncolor": "",
        "offvalue": "false",
        "offvalueType": "bool",
        "officon": "",
        "offcolor": "",
        "animate": false,
        "className": "",
        "x": 450,
        "y": 380,
        "wires": [
            [
                "5565515ee11ac12e",
                "dde578a2b0e02eb4"
            ]
        ]
    },
    {
        "id": "77b6becbac3bb10a",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "29986c92d065db26",
        "order": 4,
        "width": 3,
        "height": 1,
        "name": "",
        "label": "Downtime",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1380,
        "y": 400,
        "wires": []
    },
    {
        "id": "bed09cfef2d14564",
        "type": "debug",
        "z": "c1cfd9835acb2e31",
        "name": "debug 5",
        "active": false,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "false",
        "statusVal": "",
        "statusType": "auto",
        "x": 1800,
        "y": 380,
        "wires": []
    },
    {
        "id": "3203e1c21d4bfb30",
        "type": "ui_switch",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Status Breakdown",
        "tooltip": "",
        "group": "7a1198fbe6345632",
        "order": 3,
        "width": 0,
        "height": 0,
        "passthru": true,
        "decouple": "false",
        "topic": "BD",
        "topicType": "str",
        "style": "",
        "onvalue": "true",
        "onvalueType": "bool",
        "onicon": "",
        "oncolor": "",
        "offvalue": "false",
        "offvalueType": "bool",
        "officon": "",
        "offcolor": "",
        "animate": false,
        "className": "",
        "x": 450,
        "y": 460,
        "wires": [
            [
                "e0c2f95f986f8ad7",
                "c4ec5799a63c9163"
            ]
        ]
    },
    {
        "id": "979eb4d2fb78c656",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "29986c92d065db26",
        "order": 7,
        "width": 3,
        "height": 1,
        "name": "",
        "label": "Breakdown Time",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1410,
        "y": 480,
        "wires": []
    },
    {
        "id": "84aa6c566badbf78",
        "type": "debug",
        "z": "c1cfd9835acb2e31",
        "name": "debug 6",
        "active": false,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "false",
        "statusVal": "",
        "statusType": "auto",
        "x": 1800,
        "y": 460,
        "wires": []
    },
    {
        "id": "7d20394f337b70e8",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.payload === true) {\n    if (!context.startTime) {\n        context.startTime = new Date().getTime();\n    } else {\n        context.startTime = new Date().getTime() - context.elapsedTime;\n    }\n    context.timer = setInterval(function () {\n        var elapsedTime = new Date().getTime() - context.startTime;\n        var hours = Math.floor(elapsedTime / 3600000);\n        var minutes = Math.floor((elapsedTime - (hours * 3600000)) / 60000);\n        var seconds = Math.floor((elapsedTime - (hours * 3600000) - (minutes * 60000)) / 1000);\n        msg.payload = hours.toString().padStart(2, \"0\") + \":\" + minutes.toString().padStart(2, \"0\") + \":\" + seconds.toString().padStart(2, \"0\");\n        node.send(msg);\n        context.elapsedTime = elapsedTime;\n    }, 1000);\n} else if (msg.payload === false) {\n    clearInterval(context.timer);\n} else if (msg.payload === \"reset\") {\n    clearInterval(context.timer);\n    context.startTime = 0;\n    context.elapsedTime = 0;\n    msg.payload = \"00:00:00\";\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1190,
        "y": 300,
        "wires": [
            [
                "3a0f50f82e6a8652",
                "f2698f2ac877b1d2",
                "4fccd6288e29e28c",
                "f19d7f989d1ce803"
            ]
        ]
    },
    {
        "id": "35fa073afb73f653",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "true",
                "fromt": "bool",
                "to": "true",
                "tot": "bool"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "false",
                "fromt": "bool",
                "to": "false",
                "tot": "bool"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "payload",
                "fromt": "msg",
                "to": "reset",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 1020,
        "y": 300,
        "wires": [
            [
                "7d20394f337b70e8"
            ]
        ]
    },
    {
        "id": "5565515ee11ac12e",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "true",
                "fromt": "bool",
                "to": "true",
                "tot": "bool"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "false",
                "fromt": "bool",
                "to": "false",
                "tot": "bool"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "payload",
                "fromt": "msg",
                "to": "reset",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 1020,
        "y": 380,
        "wires": [
            [
                "7d5fec3c3cdf19ef"
            ]
        ]
    },
    {
        "id": "7d5fec3c3cdf19ef",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.payload === true) {\n    if (!context.startTime) {\n        context.startTime = new Date().getTime();\n    } else {\n        context.startTime = new Date().getTime() - context.elapsedTime;\n    }\n    context.timer = setInterval(function () {\n        var elapsedTime = new Date().getTime() - context.startTime;\n        var hours = Math.floor(elapsedTime / 3600000);\n        var minutes = Math.floor((elapsedTime - (hours * 3600000)) / 60000);\n        var seconds = Math.floor((elapsedTime - (hours * 3600000) - (minutes * 60000)) / 1000);\n        msg.payload = hours.toString().padStart(2, \"0\") + \":\" + minutes.toString().padStart(2, \"0\") + \":\" + seconds.toString().padStart(2, \"0\");\n        node.send(msg);\n        context.elapsedTime = elapsedTime;\n    }, 1000);\n} else if (msg.payload === false) {\n    clearInterval(context.timer);\n} else if (msg.payload === \"reset\") {\n    clearInterval(context.timer);\n    context.startTime = 0;\n    context.elapsedTime = 0;\n    msg.payload = \"00:00:00\";\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1190,
        "y": 380,
        "wires": [
            [
                "bed09cfef2d14564",
                "77b6becbac3bb10a",
                "5dbd633997e7f8cb"
            ]
        ]
    },
    {
        "id": "e0c2f95f986f8ad7",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "Breakdown",
                "fromt": "str",
                "to": "true",
                "tot": "bool"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "Run",
                "fromt": "str",
                "to": "false",
                "tot": "bool"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "payload",
                "fromt": "msg",
                "to": "reset",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 1020,
        "y": 460,
        "wires": [
            [
                "874b7f8be2b188d8"
            ]
        ]
    },
    {
        "id": "874b7f8be2b188d8",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.payload === true) {\n    if (!context.startTime) {\n        context.startTime = new Date().getTime();\n    } else {\n        context.startTime = new Date().getTime() - context.elapsedTime;\n    }\n    context.timer = setInterval(function () {\n        var elapsedTime = new Date().getTime() - context.startTime;\n        var hours = Math.floor(elapsedTime / 3600000);\n        var minutes = Math.floor((elapsedTime - (hours * 3600000)) / 60000);\n        var seconds = Math.floor((elapsedTime - (hours * 3600000) - (minutes * 60000)) / 1000);\n        msg.payload = hours.toString().padStart(2, \"0\") + \":\" + minutes.toString().padStart(2, \"0\") + \":\" + seconds.toString().padStart(2, \"0\");\n        node.send(msg);\n        context.elapsedTime = elapsedTime;\n    }, 1000);\n} else if (msg.payload === false) {\n    clearInterval(context.timer);\n} else if (msg.payload === \"reset\") {\n    clearInterval(context.timer);\n    context.startTime = 0;\n    context.elapsedTime = 0;\n    msg.payload = \"00:00:00\";\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1190,
        "y": 460,
        "wires": [
            [
                "979eb4d2fb78c656",
                "84aa6c566badbf78",
                "ebaa5e132a7c11b6"
            ]
        ]
    },
    {
        "id": "7a68292f1457c2a8",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}\nelse if (msg.topic === \"datprod\") {\n    msg.payload = msg.payload.target + \" \" + \"Pcs\";\n    node.send(msg)\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1300,
        "wires": [
            [
                "85b3451a0d37fdc0",
                "6da91732e84acbd3"
            ]
        ]
    },
    {
        "id": "fc18da34f81515f5",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}\nelse if (msg.topic === \"datprod\") {\n    msg.payload = msg.payload.jam + \" \" + \"Jam\";\n    node.send(msg)\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1420,
        "wires": [
            [
                "fc61a4586f6514ec",
                "c959b79059c6f3b6"
            ]
        ]
    },
    {
        "id": "accc81ad4718e858",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "e34bc21bc9269937",
        "order": 1,
        "width": "7",
        "height": "1",
        "name": "",
        "label": "Line",
        "format": "RIA 14",
        "layout": "col-center",
        "className": "",
        "x": 490,
        "y": 1320,
        "wires": []
    },
    {
        "id": "a520d053e7d58493",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "80e2142f0aa4abd6",
        "order": 8,
        "width": "3",
        "height": 1,
        "name": "",
        "label": "% Losses",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1820,
        "y": 1000,
        "wires": []
    },
    {
        "id": "c50fa9b4dab7f2c1",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var counter6 = flow.get(\"counter6\") || 0;\nvar counter7 = flow.get(\"counter7\") || 0;\nvar counter8 = flow.get(\"counter8\") || 0;\nvar counterin4 = flow.get(\"counterin4\") || 0;\nvar counterout4 = flow.get(\"counterout4\") || 0;\n\nif (msg.topic == \"reset\") {\n    counter6 = 0;\n    counter7 = 0;\n    counter8 = 0;\n    counterin4 = 0;\n    counterout4 = 0;\n} else if (msg.topic == \"input\") {\n    counter6++;\n    counter7++;\n} else if (msg.topic == \"output\") {\n    counter8++;\n} else if (msg.topic === \"inmanual2\") {\n    counterin4 = msg.payload;\n} else if (msg.topic === \"outmanual3\") {\n    counterout4 = msg.payload;\n};\n\nflow.set(\"counter6\", counter6);\nflow.set(\"counter7\", counter7);\nflow.set(\"counter8\", counter8);\nflow.set(\"counterin4\", counterin4);\nflow.set(\"counterout4\", counterout4);\n\nvar counterr6 = counter6 * 8 + counterin4;\nvar counterr7 = counter7 * 8 + counterin4;\nvar counterr8 = counter8 * 20 + counterout4;\nvar losses2 = counterr7 - counterr8;\n\nvar lossperin = losses2 / counterr6 *100;\nmsg.payload = lossperin.toFixed(2) + \" %\";\nnode.send(msg);",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1020,
        "wires": [
            [
                "a06852ed90128320"
            ]
        ]
    },
    {
        "id": "2f71695934bb22e4",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var counter9 = flow.get(\"counter9\") || 0;\nvar counter10 = flow.get(\"counter10\") || 0;\nvar counter11 = flow.get(\"counter11\") || 0;\nvar counterin5 = flow.get(\"counterin5\") || 0;\nvar counterout5 = flow.get(\"counterout5\") || 0;\n\nif (msg.topic == \"reset\") {\n    counter9 = 0;\n    counter10 = 0;\n    counter11 = 0;\n    counterin5 = 0;\n    counterout5 = 0;\n} else if (msg.topic == \"input\") {\n    counter9++;\n    counter10++;\n} else if (msg.topic == \"output\") {\n    counter11++;\n} else if (msg.topic === \"inmanual3\") {\n    counterin5 = msg.payload;\n} else if (msg.topic === \"outmanual4\") {\n    counterout5 = msg.payload;\n};\n\nflow.set(\"counter9\", counter9);\nflow.set(\"counter10\", counter10);\nflow.set(\"counter11\", counter11);\nflow.set(\"counterin5\", counterin5);\nflow.set(\"counterout5\", counterout5);\n\nvar counterr9 = counter9 * 8 + counterin5;\nvar counterr10 = counter10 * 8 + counterin5;\nvar counterr11 = counter11 * 20 + counterout5;\n\nvar outperin = counterr11 / counterr10 * 100;\nmsg.payload = outperin.toFixed(2) + \" %\";\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1100,
        "wires": [
            [
                "59aba25b0abe4187"
            ]
        ]
    },
    {
        "id": "600f0f2dcb70aa48",
        "type": "ui_gauge",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "80e2142f0aa4abd6",
        "order": 11,
        "width": "3",
        "height": "3",
        "gtype": "gage",
        "title": "Achv. Actual",
        "label": "",
        "format": "{{msg.payload}}",
        "min": "0",
        "max": "100",
        "colors": [
            "#e60000",
            "#e60000",
            "#0fe000"
        ],
        "seg1": "98.25",
        "seg2": "98.25",
        "diff": false,
        "className": "",
        "x": 1930,
        "y": 1060,
        "wires": []
    },
    {
        "id": "5318c8eab08280d6",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = \" \";\n    node.send(msg);\n}\nelse if (msg.topic === \"produk\") {\n    msg.payload = msg.payload;\n    node.send(msg)\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1240,
        "wires": [
            [
                "da35361a30e3660a",
                "1adde445d5ed26f4"
            ]
        ]
    },
    {
        "id": "4fccd6288e29e28c",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "29986c92d065db26",
        "order": 2,
        "width": "2",
        "height": 1,
        "name": "",
        "label": "GPH",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1790,
        "y": 180,
        "wires": []
    },
    {
        "id": "69650641f46baf8e",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "29986c92d065db26",
        "order": 5,
        "width": "2",
        "height": 1,
        "name": "",
        "label": "NPH",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 2890,
        "y": 740,
        "wires": []
    },
    {
        "id": "f19d7f989d1ce803",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var time1 = msg.payload.split(\":\") || 0; // memisahkan nilai jam, menit, detik pada input\n\n// menghitung total detik dari input\nvar totalSeconds = (parseInt(time1[0]) * 3600) + (parseInt(time1[1]) * 60) + parseInt(time1[2]);\n\n// menyiapkan output\nmsg.payload = totalSeconds;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 1530,
        "y": 280,
        "wires": [
            [
                "8f433f946b8ace07"
            ]
        ]
    },
    {
        "id": "5dbd633997e7f8cb",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var time2 = msg.payload.split(\":\") || 0; // memisahkan nilai jam, menit, detik pada input\n\n// menghitung total detik dari input\nvar totalSeconds2 = (parseInt(time2[0]) * 3600) + (parseInt(time2[1]) * 60) + parseInt(time2[2]);\n\n// menyiapkan output\nmsg.payload = totalSeconds2;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 1530,
        "y": 400,
        "wires": [
            [
                "ee56b37a1a3f8487"
            ]
        ]
    },
    {
        "id": "8f433f946b8ace07",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 1",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "gph",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1790,
        "y": 240,
        "wires": [
            [
                "4958dab8569e01d9",
                "39f6ac0de10f91a7",
                "963d2d5c38184187",
                "a7f6cd61f15ba5f7"
            ]
        ]
    },
    {
        "id": "ee56b37a1a3f8487",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 2",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1790,
        "y": 340,
        "wires": [
            [
                "99b74a574b9e4c33",
                "5eb6773182167a33"
            ]
        ]
    },
    {
        "id": "3cf13aed3fc708f1",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"nphh\") {\n    var nph1 = msg.payload;\n    var hours = Math.floor(nph1 / 3600);\n    var minutes = Math.floor((nph1 % 3600) / 60);\n    var seconds = Math.floor(nph1 % 60);\n    var nph = hours.toString().padStart(2, \"0\") + \":\" +\n        minutes.toString().padStart(2, \"0\") + \":\" +\n        seconds.toString().padStart(2, \"0\");\n    msg.payload = nph;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = \"00:00:00\";\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 800,
        "wires": [
            [
                "fa37d0d1fb95527e",
                "69650641f46baf8e",
                "46301be6d598bb71"
            ]
        ]
    },
    {
        "id": "fa37d0d1fb95527e",
        "type": "debug",
        "z": "c1cfd9835acb2e31",
        "name": "debug 9",
        "active": true,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "false",
        "statusVal": "",
        "statusType": "auto",
        "x": 2900,
        "y": 860,
        "wires": []
    },
    {
        "id": "ebaa5e132a7c11b6",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var time3 = msg.payload.split(\":\") || 0; // memisahkan nilai jam, menit, detik pada input\n\n// menghitung total detik dari input\nvar totalSeconds3 = (parseInt(time3[0]) * 3600) + (parseInt(time3[1]) * 60) + parseInt(time3[2]);\n\n// menyiapkan output\nmsg.payload = totalSeconds3;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 1530,
        "y": 440,
        "wires": [
            [
                "2671f9b4476ad26c"
            ]
        ]
    },
    {
        "id": "2671f9b4476ad26c",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 3",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "bdt",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1790,
        "y": 420,
        "wires": [
            [
                "6cf4cf8a197fb909",
                "377485dca708c667"
            ]
        ]
    },
    {
        "id": "6cf4cf8a197fb909",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var valu1 = flow.get(\"valu1\") || 0;\nvar valu2 = flow.get(\"valu2\") || 0;\n\nif (msg.topic === \"nph\") {\n    valu1 = msg.payload;\n    var splitit = valu1 - valu2;\n    var splittime = splitit;\n    var hours = Math.floor(splittime / 3600);\n    var minutes = Math.floor((splittime % 3600) / 60);\n    var seconds = Math.floor(splittime % 60);\n    var th = hours.toString().padStart(2, \"0\") + \":\" +\n        minutes.toString().padStart(2, \"0\") + \":\" +\n        seconds.toString().padStart(2, \"0\");\n    msg.payload = th;\n    node.send(msg);\n}\nelse if (msg.topic === \"bdt\") {\n    valu2 = msg.payload;\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = \"00:00:00\";\n    node.send(msg);\n}\nflow.set(\"valu1\", valu1);\nflow.set(\"valu2\", valu2);",
        "outputs": 1,
        "noerr": 0,
        "x": 3310,
        "y": 860,
        "wires": [
            [
                "c2885d50f3af2441",
                "03879826555baa72",
                "18b271d9f1b03184"
            ]
        ]
    },
    {
        "id": "46301be6d598bb71",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var time4 = msg.payload.split(\":\"); // memisahkan nilai jam, menit, detik pada input\n\n// menghitung total detik dari input\nvar totalSeconds4 = (parseInt(time4[0]) * 3600) + (parseInt(time4[1]) * 60) + parseInt(time4[2]);\n\n// menyiapkan output\nmsg.payload = totalSeconds4;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 2890,
        "y": 800,
        "wires": [
            [
                "a1388d802e95dc02"
            ]
        ]
    },
    {
        "id": "a1388d802e95dc02",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 4",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "nph",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 3030,
        "y": 800,
        "wires": [
            [
                "6cf4cf8a197fb909",
                "0297563e5c6f5e8b",
                "cfc54effcef46a12"
            ]
        ]
    },
    {
        "id": "18b271d9f1b03184",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "29986c92d065db26",
        "order": 8,
        "width": "2",
        "height": 1,
        "name": "",
        "label": "TH",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 3550,
        "y": 880,
        "wires": []
    },
    {
        "id": "c2885d50f3af2441",
        "type": "debug",
        "z": "c1cfd9835acb2e31",
        "name": "debug 10",
        "active": true,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "false",
        "statusVal": "",
        "statusType": "auto",
        "x": 3620,
        "y": 780,
        "wires": []
    },
    {
        "id": "03879826555baa72",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var time3 = msg.payload.split(\":\"); // memisahkan nilai jam, menit, detik pada input\n\n// menghitung total detik dari input\nvar totalSeconds3 = (parseInt(time3[0]) * 3600) + (parseInt(time3[1]) * 60) + parseInt(time3[2]);\n\n// menyiapkan output\nmsg.payload = totalSeconds3;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 3510,
        "y": 840,
        "wires": [
            [
                "9a6b1fbc0c65c0aa"
            ]
        ]
    },
    {
        "id": "9a6b1fbc0c65c0aa",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 5",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "TH",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 3670,
        "y": 840,
        "wires": [
            [
                "0297563e5c6f5e8b",
                "a7f6cd61f15ba5f7",
                "b5a64742e917ae1b"
            ]
        ]
    },
    {
        "id": "0297563e5c6f5e8b",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var valu4 = flow.get(\"valu4\") || 0;\nvar valu5 = flow.get(\"valu5\") || 0;\n\nif (msg.topic === \"nph\") {\n    valu4 = msg.payload;\n}\nelse if (msg.topic === \"TH\") {\n    valu5 = msg.payload;\n    var lineper = valu5 / valu4 * 100;\n    msg.payload = lineper.toFixed(2) + \" %\";\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    valu4 = null;\n    valu5 = null;\n    msg.payload = \"0 %\";\n    node.send(msg);\n}\nflow.set(\"valu4\", valu4);\nflow.set(\"valu5\", valu5);",
        "outputs": 1,
        "noerr": 0,
        "x": 3910,
        "y": 960,
        "wires": [
            [
                "7f9bfae96d7124eb"
            ]
        ]
    },
    {
        "id": "5ed6b0dabe4f5cf5",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "6db947571d49f1a7",
        "order": 2,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "LE",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 4390,
        "y": 920,
        "wires": []
    },
    {
        "id": "a7f6cd61f15ba5f7",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var valu7 = flow.get(\"valu7\") || 0;\nvar valu8 = flow.get(\"valu8\") || 0;\n\nif (msg.topic === \"gph\") {\n    valu7 = msg.payload;\n}\nelse if (msg.topic === \"TH\") {\n    valu8 = msg.payload;\n    var lineeff = valu8 / valu7 * 100;\n    msg.payload = lineeff.toFixed(2);\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    valu7 = null;\n    valu8 = null;\n    msg.payload = \"0 %\";\n    node.send(msg);\n}\nflow.set(\"valu7\", valu7);\nflow.set(\"valu8\", valu8);",
        "outputs": 1,
        "noerr": 0,
        "x": 3930,
        "y": 680,
        "wires": [
            [
                "561ade6c214c796b"
            ]
        ]
    },
    {
        "id": "cb2633f937b8ab9e",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "6db947571d49f1a7",
        "order": 4,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "LP",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 4390,
        "y": 740,
        "wires": []
    },
    {
        "id": "6ee0b9e30a736355",
        "type": "ui_gauge",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "6db947571d49f1a7",
        "order": 6,
        "width": "4",
        "height": "4",
        "gtype": "donut",
        "title": "Line Performance",
        "label": "%",
        "format": "{{value}}",
        "min": 0,
        "max": "100",
        "colors": [
            "#e60000",
            "#e60000",
            "#0fe000"
        ],
        "seg1": "79",
        "seg2": "79",
        "diff": false,
        "className": "",
        "x": 4430,
        "y": 780,
        "wires": []
    },
    {
        "id": "788b79be48199b7e",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "80e2142f0aa4abd6",
        "order": 12,
        "width": "6",
        "height": 1,
        "name": "",
        "label": "Catatan Produksi :",
        "format": "{{msg.payload}}",
        "layout": "row-left",
        "className": "",
        "x": 1510,
        "y": 1500,
        "wires": []
    },
    {
        "id": "7ac9948897c444ad",
        "type": "s7 in",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "mode": "single",
        "variable": "On/Off",
        "diff": true,
        "name": "Status On/Off",
        "x": 110,
        "y": 300,
        "wires": [
            [
                "a458855f3d9c6aa7"
            ]
        ]
    },
    {
        "id": "2e1945c878e2ae0d",
        "type": "s7 out",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "variable": "M1",
        "name": "M1",
        "x": 790,
        "y": 120,
        "wires": []
    },
    {
        "id": "922ac6c927e25815",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "true",
                "fromt": "bool",
                "to": "Run",
                "tot": "str"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "false",
                "fromt": "bool",
                "to": "Idle",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 820,
        "y": 180,
        "wires": [
            [
                "f2b993cd0fc78993"
            ]
        ]
    },
    {
        "id": "dde578a2b0e02eb4",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "true",
                "fromt": "bool",
                "to": "Downtime",
                "tot": "str"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "false",
                "fromt": "bool",
                "to": "Run",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 820,
        "y": 220,
        "wires": [
            [
                "f2b993cd0fc78993"
            ]
        ]
    },
    {
        "id": "c4ec5799a63c9163",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "true",
                "fromt": "bool",
                "to": "Breakdown",
                "tot": "str"
            },
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "false",
                "fromt": "bool",
                "to": "Run",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 820,
        "y": 260,
        "wires": [
            [
                "f2b993cd0fc78993"
            ]
        ]
    },
    {
        "id": "7704f5dc6dadb7d9",
        "type": "s7 in",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "mode": "single",
        "variable": "Reset",
        "diff": true,
        "name": "",
        "x": 110,
        "y": 780,
        "wires": [
            [
                "a7c3645ae6bb1a82"
            ]
        ]
    },
    {
        "id": "563e17a402b9203c",
        "type": "s7 out",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "variable": "M2",
        "name": "M2",
        "x": 430,
        "y": 820,
        "wires": []
    },
    {
        "id": "ecd4be7e28a4f584",
        "type": "change",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "rules": [
            {
                "t": "change",
                "p": "payload",
                "pt": "msg",
                "from": "true",
                "fromt": "bool",
                "to": "reset",
                "tot": "str"
            }
        ],
        "action": "",
        "property": "",
        "from": "",
        "to": "",
        "reg": false,
        "x": 520,
        "y": 780,
        "wires": [
            [
                "35fa073afb73f653",
                "5565515ee11ac12e",
                "e0c2f95f986f8ad7",
                "d42094b3c7d20015",
                "37c96ff11d59f39d",
                "2db6fe2e212b2458",
                "00422132d69f71e2",
                "c50fa9b4dab7f2c1",
                "2f71695934bb22e4",
                "5318c8eab08280d6",
                "7a68292f1457c2a8",
                "b3ab881a3276fac1",
                "fc18da34f81515f5",
                "3cf13aed3fc708f1",
                "6cf4cf8a197fb909",
                "0297563e5c6f5e8b",
                "a7f6cd61f15ba5f7",
                "18ed282925665e2f",
                "5ced481f5572b0f1",
                "832eb4a5821528b3",
                "2ca35aa8bab68b40",
                "659eb954db00c27f",
                "b7bccbbecc680c50",
                "cbf1b3a9dcfc80f7",
                "2e9e115166896e4d",
                "41300a5dea82b15e",
                "ebc72ff5483e41ff",
                "eae8be1c1566f7a6",
                "240729267a6a658c",
                "341291c64bb96471",
                "2f52c2c1007c2cac",
                "273c219ebd8627cc",
                "c58ce7d22c627ee2",
                "a38f03922ce1ee8c",
                "81a78376c593ac57",
                "bae074e36cba2958",
                "3f89cd654e75c76b",
                "89d5229bac3a4815",
                "fa98297074627964",
                "d2836109b1b6919a",
                "dd37db66b26eb6bd",
                "62a04e6521661408",
                "ccb295edb2c76fe2",
                "d543ce3f244e2fdd",
                "2d1141fcb49c75d6",
                "d3299d7c825021a0",
                "3999d1eedf1db478",
                "ba454a3382d1af5d",
                "0e709a5cdaa9db5d",
                "4ac6e4f241a1b444",
                "f0ef2488556aa30e",
                "e72dd0e4a4d1101d",
                "4297542d206a1905",
                "963d2d5c38184187",
                "5eb6773182167a33"
            ]
        ]
    },
    {
        "id": "5a3a6f1155658f2e",
        "type": "s7 in",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "mode": "single",
        "variable": "Sensor Input",
        "diff": true,
        "name": "Sensor Input",
        "x": 90,
        "y": 720,
        "wires": [
            [
                "1a72122db03bc221",
                "694335fa354cd3c8"
            ]
        ]
    },
    {
        "id": "a3371de42cb7b187",
        "type": "s7 out",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "variable": "M3",
        "name": "M3",
        "x": 470,
        "y": 660,
        "wires": []
    },
    {
        "id": "7b02194844e1c578",
        "type": "s7 in",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "mode": "single",
        "variable": "Sensor Output",
        "diff": true,
        "name": "Sensor Output",
        "x": 90,
        "y": 880,
        "wires": [
            [
                "9dfbb40fff24bf83",
                "77494a96d6ecf6d6"
            ]
        ]
    },
    {
        "id": "89ba432355685d81",
        "type": "s7 out",
        "z": "c1cfd9835acb2e31",
        "endpoint": "eb41c3ec879e0163",
        "variable": "M4",
        "name": "M4",
        "x": 490,
        "y": 940,
        "wires": []
    },
    {
        "id": "ae98073821037839",
        "type": "ui_form",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "",
        "group": "aa0ad3153fa65903",
        "order": 6,
        "width": 4,
        "height": 1,
        "options": [
            {
                "label": "Input Manual (Pcs)",
                "value": "inmanual",
                "type": "number",
                "required": true,
                "rows": null
            }
        ],
        "formValue": {
            "inmanual": ""
        },
        "payload": "",
        "submit": "submit",
        "cancel": "cancel",
        "topic": "topic",
        "topicType": "msg",
        "splitLayout": false,
        "className": "",
        "x": 110,
        "y": 580,
        "wires": [
            [
                "6347c5a0a94854e5"
            ]
        ]
    },
    {
        "id": "6347c5a0a94854e5",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var inman = msg.payload.inmanual;\nmsg.payload = inman;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 290,
        "y": 580,
        "wires": [
            [
                "25ce3f9b018e1fde",
                "134b9f803f3ff23f",
                "1835fcd4b123c653",
                "502be85ddeacac32"
            ]
        ]
    },
    {
        "id": "ae66b59e33745f51",
        "type": "ui_form",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "",
        "group": "aa0ad3153fa65903",
        "order": 7,
        "width": 4,
        "height": 1,
        "options": [
            {
                "label": "Output Manual (Pcs)",
                "value": "outmanual",
                "type": "number",
                "required": true,
                "rows": null
            }
        ],
        "formValue": {
            "outmanual": ""
        },
        "payload": "",
        "submit": "Submit",
        "cancel": "Cancel",
        "topic": "topic",
        "topicType": "msg",
        "splitLayout": "",
        "className": "",
        "x": 110,
        "y": 1060,
        "wires": [
            [
                "68e11809fdf111b8"
            ]
        ]
    },
    {
        "id": "68e11809fdf111b8",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var outman = msg.payload.outmanual;\nmsg.payload = outman;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 290,
        "y": 1060,
        "wires": [
            [
                "6a65d805a14e3c34",
                "ce3ee373fd725dc0",
                "aeeb1add5f6acb63",
                "fcf5a00e917791db"
            ]
        ]
    },
    {
        "id": "679b6aba44acca6c",
        "type": "ui_form",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "",
        "group": "aa0ad3153fa65903",
        "order": 8,
        "width": 4,
        "height": 1,
        "options": [
            {
                "label": "Output Manual (CTN)",
                "value": "outmanualctn",
                "type": "number",
                "required": true,
                "rows": null
            }
        ],
        "formValue": {
            "outmanualctn": ""
        },
        "payload": "",
        "submit": "Submit",
        "cancel": "Cancel",
        "topic": "topic",
        "topicType": "msg",
        "splitLayout": "",
        "className": "",
        "x": 110,
        "y": 1160,
        "wires": [
            [
                "dd15aa014c8a998d"
            ]
        ]
    },
    {
        "id": "dd15aa014c8a998d",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var outmanctn = msg.payload.outmanualctn;\nmsg.payload = outmanctn;\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 290,
        "y": 1160,
        "wires": [
            [
                "5f59638efedc4293"
            ]
        ]
    },
    {
        "id": "5f59638efedc4293",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Output Manual (CTN)",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 12,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "outmanualctn",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "1000000",
        "step": 1,
        "className": "",
        "x": 500,
        "y": 1160,
        "wires": [
            [
                "2db6fe2e212b2458",
                "81a78376c593ac57"
            ]
        ]
    },
    {
        "id": "25ce3f9b018e1fde",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "inmanual",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "inmanual",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "1000000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 500,
        "wires": [
            [
                "d42094b3c7d20015"
            ]
        ]
    },
    {
        "id": "134b9f803f3ff23f",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "inmanual",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "inmanual2",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "1000000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 580,
        "wires": [
            [
                "c50fa9b4dab7f2c1"
            ]
        ]
    },
    {
        "id": "1835fcd4b123c653",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "inmanual",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 5,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "inmanual3",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "1000000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 620,
        "wires": [
            [
                "2f71695934bb22e4"
            ]
        ]
    },
    {
        "id": "6a65d805a14e3c34",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 7,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "outmanual",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 1000,
        "wires": [
            [
                "37c96ff11d59f39d"
            ]
        ]
    },
    {
        "id": "ce3ee373fd725dc0",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 8,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "outmanual2",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 1040,
        "wires": [
            [
                "00422132d69f71e2"
            ]
        ]
    },
    {
        "id": "aeeb1add5f6acb63",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 9,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "outmanual3",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 1080,
        "wires": [
            [
                "c50fa9b4dab7f2c1"
            ]
        ]
    },
    {
        "id": "fcf5a00e917791db",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 10,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "outmanual4",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 1120,
        "wires": [
            [
                "2f71695934bb22e4"
            ]
        ]
    },
    {
        "id": "502be85ddeacac32",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "inmanual",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 6,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "inmanual4",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "1000000",
        "step": 1,
        "className": "",
        "x": 460,
        "y": 540,
        "wires": [
            [
                "37c96ff11d59f39d"
            ]
        ]
    },
    {
        "id": "a06852ed90128320",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "perloss",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "1000000",
        "step": 1,
        "className": "",
        "x": 1460,
        "y": 1020,
        "wires": [
            [
                "24eebb62e3d619f7",
                "f0bab70eaef6b520"
            ]
        ]
    },
    {
        "id": "24eebb62e3d619f7",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var inperloss = flow.get(\"inperloss\");\n\nif (msg.topic === \"reset\") {\n    msg.payload = \"0 %\";\n    node.send(msg);\n} else if (msg.topic === \"perloss\") {\n    inperloss = msg.payload;\n    msg.payload = inperloss.toFixed(2) + \" %\";\n    node.send(msg);\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 1670,
        "y": 1000,
        "wires": [
            [
                "a520d053e7d58493"
            ]
        ]
    },
    {
        "id": "59aba25b0abe4187",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "achv",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1520,
        "y": 1100,
        "wires": [
            [
                "2af68f97858cd61b",
                "81f4eb914063b28e"
            ]
        ]
    },
    {
        "id": "2af68f97858cd61b",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var perachv = flow.get(\"perachv\");\n\nif (msg.topic === \"reset\") {\n    msg.payload = \"0.00 %\";\n    node.send(msg);\n} else if (msg.topic === \"achv\") {\n    perachv = msg.payload;\n    msg.payload = perachv.toFixed(2) + \" %\";\n    node.send(msg);\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 1770,
        "y": 1060,
        "wires": [
            [
                "600f0f2dcb70aa48"
            ]
        ]
    },
    {
        "id": "89d5229bac3a4815",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "-1",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 1820,
        "y": 880,
        "wires": [
            [
                "e89f46e8ea8204bf"
            ]
        ]
    },
    {
        "id": "e89f46e8ea8204bf",
        "type": "ui_chart",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "ba287d2c91a9859f",
        "order": 1,
        "width": 8,
        "height": "7",
        "label": "Progress Aktual",
        "chartType": "line",
        "legend": "false",
        "xformat": "HH:mm:ss",
        "interpolate": "cubic",
        "nodata": "Silahkan klik reset !",
        "dot": false,
        "ymin": "0",
        "ymax": "",
        "removeOlder": "1",
        "removeOlderPoints": "",
        "removeOlderUnit": "60",
        "cutout": 0,
        "useOneColor": false,
        "useUTC": false,
        "colors": [
            "#1f77b4",
            "#aec7e8",
            "#ff7f0e",
            "#2ca02c",
            "#98df8a",
            "#d62728",
            "#ff9896",
            "#9467bd",
            "#c5b0d5"
        ],
        "outputs": 1,
        "useDifferentColor": false,
        "className": "",
        "x": 2120,
        "y": 920,
        "wires": [
            []
        ]
    },
    {
        "id": "561ade6c214c796b",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "elpe",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": "0.01",
        "className": "",
        "x": 4080,
        "y": 640,
        "wires": [
            [
                "341291c64bb96471",
                "864397e7a76817a9"
            ]
        ]
    },
    {
        "id": "341291c64bb96471",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var elpepe = flow.get(\"elpepe\");\n\nif (msg.topic === \"reset\") {\n    msg.payload = \"0.00 %\";\n    node.send(msg);\n} else if (msg.topic === \"elpe\") {\n    elpepe = msg.payload;\n    msg.payload = elpepe.toFixed(2) + \" %\";\n    node.send(msg);\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 4230,
        "y": 740,
        "wires": [
            [
                "cb2633f937b8ab9e",
                "6ee0b9e30a736355"
            ]
        ]
    },
    {
        "id": "7f9bfae96d7124eb",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "ele",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": "0.01",
        "className": "",
        "x": 4080,
        "y": 920,
        "wires": [
            [
                "2f52c2c1007c2cac",
                "e898782646b96b89"
            ]
        ]
    },
    {
        "id": "2f52c2c1007c2cac",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var elele = flow.get(\"elele\");\n\nif (msg.topic === \"reset\") {\n    msg.payload = \"0.00 %\";\n    node.send(msg);\n} else if (msg.topic === \"ele\") {\n    elele = msg.payload;\n    msg.payload = elele.toFixed(2) + \" %\";\n    node.send(msg);\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 4230,
        "y": 920,
        "wires": [
            [
                "5ed6b0dabe4f5cf5",
                "4548681f852d5ad7"
            ]
        ]
    },
    {
        "id": "4548681f852d5ad7",
        "type": "ui_gauge",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "6db947571d49f1a7",
        "order": 5,
        "width": "4",
        "height": "4",
        "gtype": "donut",
        "title": "Line Efficiency",
        "label": "%",
        "format": "{{value}}",
        "min": 0,
        "max": "100",
        "colors": [
            "#e60000",
            "#e60000",
            "#0fe000"
        ],
        "seg1": "89",
        "seg2": "89",
        "diff": false,
        "className": "",
        "x": 4420,
        "y": 960,
        "wires": []
    },
    {
        "id": "afc945580dea8dc7",
        "type": "inject",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "props": [
            {
                "p": "payload"
            },
            {
                "p": "topic",
                "vt": "str"
            }
        ],
        "repeat": "",
        "crontab": "",
        "once": true,
        "onceDelay": 0.1,
        "topic": "Caution !!",
        "payload": "true",
        "payloadType": "bool",
        "x": 180,
        "y": 180,
        "wires": [
            [
                "2a7f48c856c6bf7d"
            ]
        ]
    },
    {
        "id": "2a7f48c856c6bf7d",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var cautions = flow.get(\"cautions\");\n\nif (msg.topic === \"Caution !!\") {\n    cautions = \"-- Silahkan klik reset 2 kali untuk memulai program ! --\";\n    msg.payload = cautions;\n    node.send(msg);\n}\nflow.set(\"cautions\", cautions)",
        "outputs": 1,
        "noerr": 0,
        "x": 370,
        "y": 180,
        "wires": [
            [
                "50b7bef3163f5a7e"
            ]
        ]
    },
    {
        "id": "50b7bef3163f5a7e",
        "type": "ui_toast",
        "z": "c1cfd9835acb2e31",
        "position": "dialog",
        "displayTime": "3",
        "highlight": "",
        "sendall": true,
        "outputs": 1,
        "ok": "OK",
        "cancel": "",
        "raw": false,
        "className": "",
        "topic": "",
        "name": "",
        "x": 530,
        "y": 180,
        "wires": [
            []
        ]
    },
    {
        "id": "0e63a3c7b9b09a1d",
        "type": "ui_button",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "aa0ad3153fa65903",
        "order": 4,
        "width": 0,
        "height": 0,
        "passthru": true,
        "label": "Simpan Data",
        "tooltip": "",
        "color": "",
        "bgcolor": "",
        "className": "",
        "icon": "save",
        "payload": "",
        "payloadType": "date",
        "topic": "simpandata",
        "topicType": "str",
        "x": 2350,
        "y": 740,
        "wires": [
            [
                "4958dab8569e01d9",
                "39f6ac0de10f91a7",
                "3d331ed3745f31d6",
                "99b74a574b9e4c33",
                "377485dca708c667",
                "cfc54effcef46a12",
                "b5a64742e917ae1b",
                "864397e7a76817a9",
                "e898782646b96b89",
                "0ec7a8985e055268",
                "622a1cfb76eaf6bf",
                "f0bab70eaef6b520",
                "81f4eb914063b28e",
                "11291d464817e02a",
                "81fe2312e4ce1c98",
                "68b47d76ecb6e85b",
                "ed1e5b229960912c",
                "e02067d468a90383",
                "24859df1c188f8a9",
                "52b13271c8c01d05",
                "0cbd9aab79ad368c",
                "462eb3fe10db8506"
            ]
        ]
    },
    {
        "id": "4958dab8569e01d9",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var gph1 = flow.get(\"gph1\");\n\nif (msg.topic === \"gph\") {\n    gph1 = msg.payload;\n    flow.set(\"gph1\", gph1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = gph1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 260,
        "wires": [
            [
                "dbf16ea3c7c4fe38"
            ]
        ]
    },
    {
        "id": "3d331ed3745f31d6",
        "type": "date-converter",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "topic": "",
        "input": "",
        "inputType": "msg",
        "inTz": "Asia/Jakarta",
        "adjAmount": 0,
        "adjType": "days",
        "adjDir": "add",
        "format": "DD/MM/YYYY HH:mm:ss",
        "locale": "en-US",
        "output": "",
        "outputType": "msg",
        "outTz": "Asia/Jakarta",
        "x": 2720,
        "y": 140,
        "wires": [
            [
                "d9d808fa67b8e7cb"
            ],
            []
        ]
    },
    {
        "id": "f3fb461a05abc492",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C3",
        "flatten": false,
        "name": "Running Time",
        "x": 2920,
        "y": 200,
        "wires": [
            []
        ]
    },
    {
        "id": "32641933e732a243",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C4",
        "flatten": false,
        "name": "DT",
        "x": 2890,
        "y": 340,
        "wires": [
            []
        ]
    },
    {
        "id": "4b0879c5811239c9",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C5",
        "flatten": false,
        "name": "BDT",
        "x": 2890,
        "y": 420,
        "wires": [
            []
        ]
    },
    {
        "id": "cb2fcf974e57da15",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C6",
        "flatten": false,
        "name": "Produk",
        "x": 2900,
        "y": 1260,
        "wires": [
            []
        ]
    },
    {
        "id": "9fb020411bacfe74",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C7",
        "flatten": false,
        "name": "Target",
        "x": 2890,
        "y": 1320,
        "wires": [
            []
        ]
    },
    {
        "id": "cb4dda09e1199a71",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C16",
        "flatten": false,
        "name": "NPH",
        "x": 3430,
        "y": 720,
        "wires": [
            []
        ]
    },
    {
        "id": "dbf16ea3c7c4fe38",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C15",
        "flatten": false,
        "name": "GPH",
        "x": 2890,
        "y": 260,
        "wires": [
            []
        ]
    },
    {
        "id": "a492a29fc8e1a38d",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C17",
        "flatten": false,
        "name": "TH",
        "x": 4070,
        "y": 800,
        "wires": [
            []
        ]
    },
    {
        "id": "39f6ac0de10f91a7",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var gph1 = flow.get(\"gph1\");\n\nif (msg.topic === \"gph\") {\n    gph1 = msg.payload;\n    flow.set(\"gph1\", gph1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = gph1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 200,
        "wires": [
            [
                "f3fb461a05abc492"
            ]
        ]
    },
    {
        "id": "d9d808fa67b8e7cb",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C2",
        "flatten": false,
        "name": "On Run",
        "x": 2900,
        "y": 140,
        "wires": [
            []
        ]
    },
    {
        "id": "99b74a574b9e4c33",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var jam1 = flow.get(\"jam1\");\n\nif (msg.topic === \"jam\") {\n    jam1 = msg.payload;\n    flow.set(\"jam1\", jam1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = jam1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 340,
        "wires": [
            [
                "32641933e732a243"
            ]
        ]
    },
    {
        "id": "377485dca708c667",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var bdt1 = flow.get(\"bdt1\");\n\nif (msg.topic === \"bdt\") {\n    bdt1 = msg.payload;\n    flow.set(\"bdt1\", bdt1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = bdt1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 420,
        "wires": [
            [
                "4b0879c5811239c9"
            ]
        ]
    },
    {
        "id": "cfc54effcef46a12",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var nph1 = flow.get(\"nph1\");\n\nif (msg.topic === \"nph\") {\n    nph1 = msg.payload;\n    flow.set(\"nph1\", nph1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = nph1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 3290,
        "y": 720,
        "wires": [
            [
                "cb4dda09e1199a71"
            ]
        ]
    },
    {
        "id": "b5a64742e917ae1b",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var th1 = flow.get(\"th1\");\n\nif (msg.topic === \"TH\") {\n    th1 = msg.payload;\n    flow.set(\"th1\", th1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = th1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 3910,
        "y": 800,
        "wires": [
            [
                "a492a29fc8e1a38d"
            ]
        ]
    },
    {
        "id": "864397e7a76817a9",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var elpe1 = flow.get(\"elpe1\");\n\nif (msg.topic === \"elpe\") {\n    elpe1 = msg.payload;\n    flow.set(\"elpe1\", elpe1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = elpe1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 4230,
        "y": 700,
        "wires": [
            [
                "98f04a6f53a484a1"
            ]
        ]
    },
    {
        "id": "98f04a6f53a484a1",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C19",
        "flatten": false,
        "name": "LP",
        "x": 4390,
        "y": 700,
        "wires": [
            []
        ]
    },
    {
        "id": "e898782646b96b89",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var ele1 = flow.get(\"ele1\");\n\nif (msg.topic === \"ele\") {\n    ele1 = msg.payload;\n    flow.set(\"ele1\", ele1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = ele1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 4230,
        "y": 880,
        "wires": [
            [
                "3f1aee5e36225d27"
            ]
        ]
    },
    {
        "id": "3f1aee5e36225d27",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C18",
        "flatten": false,
        "name": "LE",
        "x": 4390,
        "y": 880,
        "wires": [
            []
        ]
    },
    {
        "id": "24859df1c188f8a9",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var inpcs1 = flow.get(\"inpcs1\");\n\nif (msg.topic === \"inpcs\") {\n    inpcs1 = msg.payload;\n    flow.set(\"inpcs1\", inpcs1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = inpcs1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 600,
        "wires": [
            [
                "5f5745d3a516cf2d"
            ]
        ]
    },
    {
        "id": "5f5745d3a516cf2d",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C10",
        "flatten": false,
        "name": "Input Pcs",
        "x": 2900,
        "y": 600,
        "wires": [
            []
        ]
    },
    {
        "id": "4c4bc915b7a526e3",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 3",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "inpcs",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1030,
        "y": 600,
        "wires": [
            [
                "24859df1c188f8a9"
            ]
        ]
    },
    {
        "id": "8ac7dba5b9f0d770",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 3",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "lossya",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1030,
        "y": 680,
        "wires": [
            [
                "52b13271c8c01d05"
            ]
        ]
    },
    {
        "id": "52b13271c8c01d05",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var lossya1 = flow.get(\"lossya1\");\n\nif (msg.topic === \"lossya\") {\n    lossya1 = msg.payload;\n    flow.set(\"lossya1\", lossya1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = lossya1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 680,
        "wires": [
            [
                "cb5e90536c5a1362"
            ]
        ]
    },
    {
        "id": "cb5e90536c5a1362",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C13",
        "flatten": false,
        "name": "Losses Pcs",
        "x": 2910,
        "y": 680,
        "wires": [
            []
        ]
    },
    {
        "id": "60391e289dd05392",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 3",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "outctn",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1470,
        "y": 840,
        "wires": [
            [
                "0ec7a8985e055268",
                "81a78376c593ac57"
            ]
        ]
    },
    {
        "id": "0ec7a8985e055268",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var outctn1 = flow.get(\"outctn1\");\n\nif (msg.topic === \"outctn\") {\n    outctn1 = msg.payload;\n    flow.set(\"outctn1\", outctn1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = outctn1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 900,
        "wires": [
            [
                "3b65ac27906655da"
            ]
        ]
    },
    {
        "id": "3b65ac27906655da",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C12",
        "flatten": false,
        "name": "Output CTN",
        "x": 2910,
        "y": 900,
        "wires": [
            []
        ]
    },
    {
        "id": "4994b08e85968849",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 3",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "outpcs",
        "topicType": "str",
        "format": "{{value}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 530,
        "y": 1620,
        "wires": [
            [
                "622a1cfb76eaf6bf",
                "ec6a88611c619ab8",
                "6e23e8885f025492",
                "07f29095d88744c0",
                "4418a47392f4e19a",
                "e44a3065647d9a79",
                "c8e377c9eba7d57d",
                "fdcd2b9e491ce340",
                "da7bd4baf1b8b6b2",
                "fa39bb1de7088817",
                "702cc113f2d07097",
                "bee941880412897b",
                "55319ae4885c49d6"
            ]
        ]
    },
    {
        "id": "622a1cfb76eaf6bf",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var outpcs1 = flow.get(\"outpcs1\");\n\nif (msg.topic === \"outpcs\") {\n    outpcs1 = msg.payload;\n    flow.set(\"outpcs1\", outpcs1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = outpcs1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2710,
        "y": 1620,
        "wires": [
            [
                "ee01f6df602e388b"
            ]
        ]
    },
    {
        "id": "ee01f6df602e388b",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C11",
        "flatten": false,
        "name": "Output Pcs",
        "x": 2890,
        "y": 1620,
        "wires": [
            []
        ]
    },
    {
        "id": "f0bab70eaef6b520",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var perloss1 = flow.get(\"perloss1\");\n\nif (msg.topic === \"perloss\") {\n    perloss1 = msg.payload;\n    flow.set(\"perloss1\", perloss1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = perloss1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 1020,
        "wires": [
            [
                "e6396e64e108f517"
            ]
        ]
    },
    {
        "id": "e6396e64e108f517",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C14",
        "flatten": false,
        "name": "Persen Losses",
        "x": 2920,
        "y": 1020,
        "wires": [
            []
        ]
    },
    {
        "id": "81f4eb914063b28e",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var achv1 = flow.get(\"achv1\");\n\nif (msg.topic === \"perloss\") {\n    achv1 = msg.payload;\n    flow.set(\"achv1\", achv1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = achv1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 1100,
        "wires": [
            [
                "3f2e223f47fb93b1"
            ]
        ]
    },
    {
        "id": "3f2e223f47fb93b1",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C21",
        "flatten": false,
        "name": "Persen Achv",
        "x": 2910,
        "y": 1100,
        "wires": [
            []
        ]
    },
    {
        "id": "81fe2312e4ce1c98",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var prod1 = flow.get(\"prod1\");\n\nif (msg.topic === \"prod\") {\n    prod1 = msg.payload;\n    flow.set(\"prod1\", prod1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = prod1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 1260,
        "wires": [
            [
                "cb2fcf974e57da15"
            ]
        ]
    },
    {
        "id": "68b47d76ecb6e85b",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var tarprod1 = flow.get(\"tarprod1\");\n\nif (msg.topic === \"tarprod\") {\n    tarprod1 = msg.payload;\n    flow.set(\"tarprod1\", tarprod1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = tarprod1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 1320,
        "wires": [
            [
                "9fb020411bacfe74"
            ]
        ]
    },
    {
        "id": "1adde445d5ed26f4",
        "type": "ui_text_input",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Produk",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "passthru": true,
        "mode": "text",
        "delay": "10",
        "topic": "prod",
        "sendOnBlur": true,
        "className": "",
        "topicType": "str",
        "x": 1720,
        "y": 1260,
        "wires": [
            [
                "81fe2312e4ce1c98"
            ]
        ]
    },
    {
        "id": "6da91732e84acbd3",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Target",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "tarprod",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000000",
        "step": 1,
        "className": "",
        "x": 1470,
        "y": 1320,
        "wires": [
            [
                "68b47d76ecb6e85b",
                "b3ab881a3276fac1",
                "81a78376c593ac57"
            ]
        ]
    },
    {
        "id": "7463ae45b581d220",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Speed",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "speedy",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000000",
        "step": 1,
        "className": "",
        "x": 2150,
        "y": 1360,
        "wires": [
            [
                "ed1e5b229960912c"
            ]
        ]
    },
    {
        "id": "ed1e5b229960912c",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var speedy1 = flow.get(\"speedy1\");\n\nif (msg.topic === \"speedy\") {\n    speedy1 = msg.payload;\n    flow.set(\"speedy1\", speedy1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = speedy1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 1360,
        "wires": [
            [
                "8bbda4483b0bd2b9"
            ]
        ]
    },
    {
        "id": "8bbda4483b0bd2b9",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C9",
        "flatten": false,
        "name": "Speed",
        "x": 2890,
        "y": 1360,
        "wires": [
            []
        ]
    },
    {
        "id": "c959b79059c6f3b6",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Target Jam",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "tarjam",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "24",
        "step": 1,
        "className": "",
        "x": 1730,
        "y": 1420,
        "wires": [
            [
                "e02067d468a90383",
                "b3ab881a3276fac1"
            ]
        ]
    },
    {
        "id": "e02067d468a90383",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var tarjam1 = flow.get(\"tarjam1\");\n\nif (msg.topic === \"tarjam\") {\n    tarjam1 = msg.payload;\n    flow.set(\"tarjam1\", tarjam1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = tarjam1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 1420,
        "wires": [
            [
                "31147a6f38df9987"
            ]
        ]
    },
    {
        "id": "31147a6f38df9987",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C8",
        "flatten": false,
        "name": "Target Jam",
        "x": 2910,
        "y": 1420,
        "wires": [
            []
        ]
    },
    {
        "id": "11291d464817e02a",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var note1 = flow.get(\"note1\");\n\nif (msg.topic === \"note\") {\n    note1 = msg.payload;\n    flow.set(\"note1\", note1);\n}\nelse if (msg.topic === \"simpandata\") {\n    msg.payload = note1;\n    node.send(msg);\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = null;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 1480,
        "wires": [
            [
                "7b77127c73bd9e41"
            ]
        ]
    },
    {
        "id": "7b77127c73bd9e41",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!C20",
        "flatten": false,
        "name": "Catatan Produksi",
        "x": 2930,
        "y": 1480,
        "wires": [
            []
        ]
    },
    {
        "id": "ec6a88611c619ab8",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "1",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 1720,
        "wires": [
            [
                "d2836109b1b6919a"
            ]
        ]
    },
    {
        "id": "d2836109b1b6919a",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 1720,
        "wires": [
            [
                "0b7373baf020bb29"
            ]
        ]
    },
    {
        "id": "0b7373baf020bb29",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "1",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam1",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 1720,
        "wires": [
            [
                "18ed282925665e2f"
            ]
        ]
    },
    {
        "id": "af4e9891137bff27",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 2,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-1",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 1720,
        "wires": []
    },
    {
        "id": "21a81224cf86dafa",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 3,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-2",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 1800,
        "wires": []
    },
    {
        "id": "5cca91cf0661a047",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 4,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-3",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 1880,
        "wires": []
    },
    {
        "id": "1c29fcacfe2f737d",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 5,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-4",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 1960,
        "wires": []
    },
    {
        "id": "6e23e8885f025492",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "2",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 1800,
        "wires": [
            [
                "dd37db66b26eb6bd"
            ]
        ]
    },
    {
        "id": "dd37db66b26eb6bd",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 1800,
        "wires": [
            [
                "8ef1481a0209409b"
            ]
        ]
    },
    {
        "id": "8ef1481a0209409b",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "2",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam2",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 1800,
        "wires": [
            [
                "5ced481f5572b0f1"
            ]
        ]
    },
    {
        "id": "07f29095d88744c0",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "3",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 1880,
        "wires": [
            [
                "62a04e6521661408"
            ]
        ]
    },
    {
        "id": "62a04e6521661408",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 1880,
        "wires": [
            [
                "f02021177fd82cf0"
            ]
        ]
    },
    {
        "id": "f02021177fd82cf0",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "3",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam3",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 1880,
        "wires": [
            [
                "832eb4a5821528b3"
            ]
        ]
    },
    {
        "id": "4418a47392f4e19a",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "4",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 1960,
        "wires": [
            [
                "ccb295edb2c76fe2"
            ]
        ]
    },
    {
        "id": "ccb295edb2c76fe2",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 1960,
        "wires": [
            [
                "58ebd233ae93e964"
            ]
        ]
    },
    {
        "id": "58ebd233ae93e964",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "4",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam4",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 1960,
        "wires": [
            [
                "2ca35aa8bab68b40"
            ]
        ]
    },
    {
        "id": "e44a3065647d9a79",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "5",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2040,
        "wires": [
            [
                "d543ce3f244e2fdd"
            ]
        ]
    },
    {
        "id": "c8e377c9eba7d57d",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "6",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2120,
        "wires": [
            [
                "2d1141fcb49c75d6"
            ]
        ]
    },
    {
        "id": "d543ce3f244e2fdd",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2040,
        "wires": [
            [
                "7889ee32489a0f52"
            ]
        ]
    },
    {
        "id": "2d1141fcb49c75d6",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2120,
        "wires": [
            [
                "9a455d81b3ac56fb"
            ]
        ]
    },
    {
        "id": "fdcd2b9e491ce340",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "7",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2200,
        "wires": [
            [
                "d3299d7c825021a0"
            ]
        ]
    },
    {
        "id": "d3299d7c825021a0",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2200,
        "wires": [
            [
                "878c21a778cca73d"
            ]
        ]
    },
    {
        "id": "7889ee32489a0f52",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "5",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam5",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2040,
        "wires": [
            [
                "659eb954db00c27f"
            ]
        ]
    },
    {
        "id": "9a455d81b3ac56fb",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "6",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam6",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2120,
        "wires": [
            [
                "b7bccbbecc680c50"
            ]
        ]
    },
    {
        "id": "878c21a778cca73d",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "7",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam7",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2200,
        "wires": [
            [
                "cbf1b3a9dcfc80f7"
            ]
        ]
    },
    {
        "id": "da7bd4baf1b8b6b2",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "8",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2280,
        "wires": [
            [
                "3999d1eedf1db478"
            ]
        ]
    },
    {
        "id": "3999d1eedf1db478",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2280,
        "wires": [
            [
                "b0745cfebf10edc1"
            ]
        ]
    },
    {
        "id": "b0745cfebf10edc1",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "8",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam8",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2280,
        "wires": [
            [
                "2e9e115166896e4d"
            ]
        ]
    },
    {
        "id": "8dfcdc9b456e7e81",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 6,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-5",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 2040,
        "wires": []
    },
    {
        "id": "ef73f3114f29b268",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 7,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-6",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 2120,
        "wires": []
    },
    {
        "id": "962adad99131d23d",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 8,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-7",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 2200,
        "wires": []
    },
    {
        "id": "bee8416cff7743cf",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 9,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-8",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 2280,
        "wires": []
    },
    {
        "id": "18ed282925665e2f",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam1\") {\n    var jam1ya = msg.payload;\n    msg.payload = jam1ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1720,
        "wires": [
            [
                "af4e9891137bff27"
            ]
        ]
    },
    {
        "id": "5ced481f5572b0f1",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam2\") {\n    var jam2ya = msg.payload;\n    msg.payload = jam2ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1800,
        "wires": [
            [
                "21a81224cf86dafa"
            ]
        ]
    },
    {
        "id": "832eb4a5821528b3",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam3\") {\n    var jam3ya = msg.payload;\n    msg.payload = jam3ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1880,
        "wires": [
            [
                "5cca91cf0661a047"
            ]
        ]
    },
    {
        "id": "2ca35aa8bab68b40",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam4\") {\n    var jam4ya = msg.payload;\n    msg.payload = jam4ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1960,
        "wires": [
            [
                "1c29fcacfe2f737d"
            ]
        ]
    },
    {
        "id": "659eb954db00c27f",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam5\") {\n    var jam5ya = msg.payload;\n    msg.payload = jam5ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2040,
        "wires": [
            [
                "8dfcdc9b456e7e81"
            ]
        ]
    },
    {
        "id": "b7bccbbecc680c50",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam6\") {\n    var jam6ya = msg.payload;\n    msg.payload = jam6ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2120,
        "wires": [
            [
                "ef73f3114f29b268"
            ]
        ]
    },
    {
        "id": "cbf1b3a9dcfc80f7",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam7\") {\n    var jam7ya = msg.payload;\n    msg.payload = jam7ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2200,
        "wires": [
            [
                "962adad99131d23d"
            ]
        ]
    },
    {
        "id": "2e9e115166896e4d",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam8\") {\n    var jam8ya = msg.payload;\n    msg.payload = jam8ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2280,
        "wires": [
            [
                "bee8416cff7743cf"
            ]
        ]
    },
    {
        "id": "fa39bb1de7088817",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "9",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2360,
        "wires": [
            [
                "ba454a3382d1af5d"
            ]
        ]
    },
    {
        "id": "702cc113f2d07097",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "10",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2440,
        "wires": [
            [
                "0e709a5cdaa9db5d"
            ]
        ]
    },
    {
        "id": "ba454a3382d1af5d",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2360,
        "wires": [
            [
                "fd43d1afc1c8f02d"
            ]
        ]
    },
    {
        "id": "0e709a5cdaa9db5d",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2440,
        "wires": [
            [
                "accffeb6936f20db"
            ]
        ]
    },
    {
        "id": "bee941880412897b",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "11",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2520,
        "wires": [
            [
                "f0ef2488556aa30e"
            ]
        ]
    },
    {
        "id": "f0ef2488556aa30e",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2520,
        "wires": [
            [
                "27fc121e0e7158d4"
            ]
        ]
    },
    {
        "id": "fd43d1afc1c8f02d",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "9",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam9",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2360,
        "wires": [
            [
                "41300a5dea82b15e"
            ]
        ]
    },
    {
        "id": "accffeb6936f20db",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "10",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam10",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2440,
        "wires": [
            [
                "ebc72ff5483e41ff"
            ]
        ]
    },
    {
        "id": "27fc121e0e7158d4",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "11",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam11",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2520,
        "wires": [
            [
                "eae8be1c1566f7a6"
            ]
        ]
    },
    {
        "id": "55319ae4885c49d6",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "nul",
        "op2type": "payl",
        "duration": "12",
        "extend": false,
        "overrideDelay": false,
        "units": "min",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 790,
        "y": 2600,
        "wires": [
            [
                "4ac6e4f241a1b444"
            ]
        ]
    },
    {
        "id": "4ac6e4f241a1b444",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "payl",
        "duration": "0",
        "extend": false,
        "overrideDelay": false,
        "units": "s",
        "reset": "reset",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 960,
        "y": 2600,
        "wires": [
            [
                "dbc2d0d3d685c6be"
            ]
        ]
    },
    {
        "id": "dbc2d0d3d685c6be",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "12",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 4,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "jam12",
        "topicType": "str",
        "format": "{{msg.payload}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1130,
        "y": 2600,
        "wires": [
            [
                "240729267a6a658c"
            ]
        ]
    },
    {
        "id": "6ec771df26088693",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 10,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-9",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1500,
        "y": 2360,
        "wires": []
    },
    {
        "id": "81f55f2d3aac2c59",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 11,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-10",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1510,
        "y": 2440,
        "wires": []
    },
    {
        "id": "864b57819ef98ce8",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 12,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-11",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1510,
        "y": 2520,
        "wires": []
    },
    {
        "id": "d954795d6a4f1536",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "ba287d2c91a9859f",
        "order": 13,
        "width": 2,
        "height": 1,
        "name": "",
        "label": "Jam ke-12",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1510,
        "y": 2600,
        "wires": []
    },
    {
        "id": "41300a5dea82b15e",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam9\") {\n    var jam9ya = msg.payload;\n    msg.payload = jam9ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2360,
        "wires": [
            [
                "6ec771df26088693"
            ]
        ]
    },
    {
        "id": "ebc72ff5483e41ff",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam10\") {\n    var jam10ya = msg.payload;\n    msg.payload = jam10ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2440,
        "wires": [
            [
                "81f55f2d3aac2c59"
            ]
        ]
    },
    {
        "id": "eae8be1c1566f7a6",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam11\") {\n    var jam11ya = msg.payload;\n    msg.payload = jam11ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2520,
        "wires": [
            [
                "864b57819ef98ce8"
            ]
        ]
    },
    {
        "id": "240729267a6a658c",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam12\") {\n    var jam12ya = msg.payload;\n    msg.payload = jam12ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 2600,
        "wires": [
            [
                "d954795d6a4f1536"
            ]
        ]
    },
    {
        "id": "0cbd9aab79ad368c",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"simpandata\") {\n    msg.payload = msg.payload;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2690,
        "y": 520,
        "wires": [
            [
                "93ccf77cb5a6297c"
            ]
        ]
    },
    {
        "id": "e77d8adec88a8a96",
        "type": "ui_toast",
        "z": "c1cfd9835acb2e31",
        "position": "top right",
        "displayTime": "3",
        "highlight": "",
        "sendall": true,
        "outputs": 0,
        "ok": "OK",
        "cancel": "",
        "raw": false,
        "className": "",
        "topic": "",
        "name": "",
        "x": 3250,
        "y": 600,
        "wires": []
    },
    {
        "id": "b3ca493ad285f106",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"Caution !!\") {\n    msg.payload = \"Data telah berhasil disimpan!\";\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 3050,
        "y": 520,
        "wires": [
            [
                "e77d8adec88a8a96"
            ]
        ]
    },
    {
        "id": "93ccf77cb5a6297c",
        "type": "ui_button",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "passthru": true,
        "label": "Simpan Data",
        "tooltip": "",
        "color": "",
        "bgcolor": "",
        "className": "",
        "icon": "save",
        "payload": "",
        "payloadType": "date",
        "topic": "Caution !!",
        "topicType": "str",
        "x": 2870,
        "y": 520,
        "wires": [
            [
                "b3ca493ad285f106"
            ]
        ]
    },
    {
        "id": "273c219ebd8627cc",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var gph1 = flow.get(\"gph1\") || 0;\nvar dt1 = flow.get(\"dt1\") || 0;\n\nif (msg.topic === \"dtfix\") {\n    dt1 = msg.payload;\n    flow.set(\"dt1\", dt1);\n} \nelse if (msg.topic === \"gphfix\") {\n    gph1 = msg.payload;\n    flow.set(\"gph1\", gph1);\n    var nph = gph1 - dt1;\n    msg.payload = nph;\n    return msg;\n}\nelse if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 2390,
        "y": 380,
        "wires": [
            [
                "baaf44b03750c7de"
            ]
        ]
    },
    {
        "id": "da7a1b45d3e64368",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "80e2142f0aa4abd6",
        "order": 1,
        "width": "3",
        "height": "1",
        "name": "",
        "label": "Target (CTN)",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1490,
        "y": 1540,
        "wires": []
    },
    {
        "id": "81a78376c593ac57",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var counter20 = flow.get(\"counter20\") || 0;\nvar counter21 = flow.get(\"counter21\") || 0;\nvar counterout11 = flow.get(\"counterout11\") || 0;\n\nif (msg.topic == \"reset\") {\n    counter20 = 0;\n    counter21 = 0;\n    counterout11 = 0;\n} else if (msg.topic == \"tarprod\") {\n    counter20 = msg.payload;\n   } else if (msg.topic == \"outctn\") {\n    counter21 = msg.payload;\n} else if (msg.topic === \"outmanualctn\") {\n    counterout11 = msg.payload;\n};\n\nflow.set(\"counter20\", counter20);\nflow.set(\"counter21\", counter21);\nflow.set(\"counterout11\", counterout11);\n\nvar outputget = counter21 + counterout11;\n\nvar achtarget = outputget / counter20 * 100;\nmsg.payload = achtarget.toFixed(2) + \" %\";\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 1730,
        "y": 1200,
        "wires": [
            [
                "82d0ad3e930619ac"
            ]
        ]
    },
    {
        "id": "82d0ad3e930619ac",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "achv",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1940,
        "y": 1200,
        "wires": [
            [
                "a38f03922ce1ee8c"
            ]
        ]
    },
    {
        "id": "a38f03922ce1ee8c",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var perachv = flow.get(\"perachv\");\n\nif (msg.topic === \"reset\") {\n    msg.payload = \"0.00 %\";\n    node.send(msg);\n} else if (msg.topic === \"achv\") {\n    perachv = msg.payload;\n    msg.payload = perachv.toFixed(2) + \" %\";\n    node.send(msg);\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 2150,
        "y": 1200,
        "wires": [
            [
                "2bc43c927b1d3f10"
            ]
        ]
    },
    {
        "id": "2bc43c927b1d3f10",
        "type": "ui_gauge",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "80e2142f0aa4abd6",
        "order": 10,
        "width": "3",
        "height": "3",
        "gtype": "gage",
        "title": "Achv. Target",
        "label": "",
        "format": "{{msg.payload}}",
        "min": "0",
        "max": "100",
        "colors": [
            "#e60000",
            "#e60000",
            "#0fe000"
        ],
        "seg1": "98.25",
        "seg2": "98.25",
        "diff": false,
        "className": "",
        "x": 2370,
        "y": 1200,
        "wires": []
    },
    {
        "id": "c58ce7d22c627ee2",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}\nelse if (msg.topic === \"datprod\") {\n    msg.payload = msg.payload.target;\n    node.send(msg)\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1540,
        "wires": [
            [
                "da7a1b45d3e64368"
            ]
        ]
    },
    {
        "id": "462eb3fe10db8506",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"simpandata\") {\n    msg.payload = true;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2930,
        "y": 640,
        "wires": [
            [
                "594690539883eeb0"
            ]
        ]
    },
    {
        "id": "3d04ccae71e80e20",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!A1",
        "flatten": false,
        "name": "Record",
        "x": 3440,
        "y": 660,
        "wires": [
            [
                "f9d87eb6876abf96"
            ]
        ]
    },
    {
        "id": "594690539883eeb0",
        "type": "delay",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "pauseType": "delay",
        "timeout": "5",
        "timeoutUnits": "seconds",
        "rate": "1",
        "nbRateUnits": "1",
        "rateUnits": "second",
        "randomFirst": "1",
        "randomLast": "5",
        "randomUnits": "seconds",
        "drop": false,
        "allowrate": false,
        "outputs": 1,
        "x": 3240,
        "y": 660,
        "wires": [
            [
                "3d04ccae71e80e20"
            ]
        ]
    },
    {
        "id": "f9d87eb6876abf96",
        "type": "GSheet",
        "z": "c1cfd9835acb2e31",
        "creds": "3db337b444e5d026",
        "method": "update",
        "action": "",
        "sheet": "1N2H8_toyttYMimrHg98W4C0nwJvaMtM0AKqWJ2OxZ1Q",
        "cells": "Input!H1",
        "flatten": false,
        "name": "Record",
        "x": 3620,
        "y": 660,
        "wires": [
            []
        ]
    },
    {
        "id": "992e32fc5eb6370c",
        "type": "ui_form",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Data produksi",
        "group": "3323f7416b9a5747",
        "order": 3,
        "width": 0,
        "height": 0,
        "options": [
            {
                "label": "Target Produksi",
                "value": "target",
                "type": "number",
                "required": true,
                "rows": null
            },
            {
                "label": "Target Jam",
                "value": "jam",
                "type": "number",
                "required": true,
                "rows": null
            },
            {
                "label": "Target LE",
                "value": "targetle",
                "type": "number",
                "required": true,
                "rows": null
            },
            {
                "label": "Target LP",
                "value": "targetlp",
                "type": "number",
                "required": true,
                "rows": null
            },
            {
                "label": "Catatan Produksi",
                "value": "note",
                "type": "text",
                "required": false,
                "rows": null
            }
        ],
        "formValue": {
            "target": "",
            "jam": "",
            "targetle": "",
            "targetlp": "",
            "note": ""
        },
        "payload": "",
        "submit": "submit",
        "cancel": "cancel",
        "topic": "datprod",
        "topicType": "str",
        "splitLayout": true,
        "className": "",
        "x": 520,
        "y": 1380,
        "wires": [
            [
                "7a68292f1457c2a8",
                "c58ce7d22c627ee2",
                "fc18da34f81515f5",
                "bae074e36cba2958",
                "3f89cd654e75c76b",
                "4297542d206a1905"
            ]
        ]
    },
    {
        "id": "4879de523656f944",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "6db947571d49f1a7",
        "order": 1,
        "width": "2",
        "height": 1,
        "name": "",
        "label": "Target LE",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1480,
        "y": 1600,
        "wires": []
    },
    {
        "id": "80617c65d31231fe",
        "type": "ui_text",
        "z": "c1cfd9835acb2e31",
        "group": "6db947571d49f1a7",
        "order": 3,
        "width": "2",
        "height": 1,
        "name": "",
        "label": "Target LP",
        "format": "{{msg.payload}}",
        "layout": "col-center",
        "className": "",
        "x": 1480,
        "y": 1640,
        "wires": []
    },
    {
        "id": "3f89cd654e75c76b",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = \"0.00 %\";\n    return msg;\n}\nelse if (msg.topic === \"datprod\") {\n    var targetlp1 = msg.payload.targetlp;\n    msg.payload = targetlp1 + \" %\";\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1640,
        "wires": [
            [
                "80617c65d31231fe"
            ]
        ]
    },
    {
        "id": "bae074e36cba2958",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = \"0.00 %\";\n    return msg;\n}\nelse if (msg.topic === \"datprod\") {\n    var targetle1 = msg.payload.targetle;\n    msg.payload = targetle1 + \" %\";\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1600,
        "wires": [
            [
                "4879de523656f944"
            ]
        ]
    },
    {
        "id": "4297542d206a1905",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = \" \";\n    node.send(msg);\n}\nelse if (msg.topic === \"datprod\") {\n    var catt = msg.payload.note;\n    msg.payload = catt;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1310,
        "y": 1480,
        "wires": [
            [
                "11291d464817e02a",
                "788b79be48199b7e"
            ]
        ]
    },
    {
        "id": "8863e0a4048d92da",
        "type": "ui_text_input",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "passthru": true,
        "mode": "text",
        "delay": "10",
        "topic": "produk",
        "sendOnBlur": true,
        "className": "",
        "topicType": "str",
        "x": 1140,
        "y": 1240,
        "wires": [
            [
                "5318c8eab08280d6"
            ]
        ]
    },
    {
        "id": "e72dd0e4a4d1101d",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = \" \";\n    node.send(msg);\n}\nelse if (msg.topic === \"pilproduk\") {\n    msg.payload = msg.payload;\n    node.send(msg)\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 970,
        "y": 1240,
        "wires": [
            [
                "8863e0a4048d92da"
            ]
        ]
    },
    {
        "id": "fa98297074627964",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    return msg;\n}\nelse if (msg.topic === \"jam1\") {\n    var jam1ya = msg.payload;\n    msg.payload = jam1ya;\n    return msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 2150,
        "y": 700,
        "wires": [
            []
        ]
    },
    {
        "id": "963d2d5c38184187",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = 0;\n    node.send(msg);\n}\nelse if (msg.topic === \"gph\") {\n    context.value1 = msg.payload;\n    msg.payload = context.value1;\n    node.send(msg);\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 2030,
        "y": 280,
        "wires": [
            [
                "931cd0f6da6b41c5"
            ]
        ]
    },
    {
        "id": "931cd0f6da6b41c5",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "GPH Fix",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "gphfix",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 2200,
        "y": 280,
        "wires": [
            [
                "273c219ebd8627cc"
            ]
        ]
    },
    {
        "id": "5eb6773182167a33",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var jamm = 0;\n\nif (msg.topic === \"reset\") {\n    msg.payload = jamm;\n    node.send(msg);\n}\nelse if (msg.topic === \"jam\") {\n    context.value1 = msg.payload;\n    msg.payload = context.value1;\n    node.send(msg);\n}\n",
        "outputs": 1,
        "noerr": 0,
        "x": 2030,
        "y": 360,
        "wires": [
            [
                "d868afd373847d15"
            ]
        ]
    },
    {
        "id": "d868afd373847d15",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "DT Fix",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "dtfix",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 2190,
        "y": 360,
        "wires": [
            [
                "273c219ebd8627cc"
            ]
        ]
    },
    {
        "id": "c64dd086f3eda962",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "var timer;\nvar counter = 0;\n\nif (msg.payload == true) {\n    if (!timer) {\n        timer = setInterval(function () {\n            counter++;\n            node.send({ payload: counter });\n        }, 1000);\n    }\n} else {\n    clearInterval(timer);\n    timer = null;\n    counter = 0;\n    node.send({ payload: counter });\n}\n\nreturn null;\n",
        "outputs": 1,
        "noerr": 0,
        "x": 1370,
        "y": 360,
        "wires": [
            []
        ]
    },
    {
        "id": "baaf44b03750c7de",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "numeric",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 43,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "nphh",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "1000000",
        "step": 1,
        "className": "",
        "x": 2440,
        "y": 440,
        "wires": [
            [
                "3cf13aed3fc708f1"
            ]
        ]
    },
    {
        "id": "e83fdd1604fc3516",
        "type": "inject",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "props": [
            {
                "p": "payload"
            },
            {
                "p": "topic",
                "vt": "str"
            }
        ],
        "repeat": "",
        "crontab": "",
        "once": false,
        "onceDelay": 0.1,
        "topic": "",
        "payload": "",
        "payloadType": "date",
        "x": 1540,
        "y": 160,
        "wires": [
            []
        ]
    },
    {
        "id": "05a99143f595bd05",
        "type": "ui_numeric",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "Flow 3",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "wrap": false,
        "passthru": true,
        "topic": "inpcs",
        "topicType": "str",
        "format": "{{value}}",
        "min": 0,
        "max": "100000",
        "step": 1,
        "className": "",
        "x": 1610,
        "y": 100,
        "wires": [
            []
        ]
    },
    {
        "id": "bbcc37d1deb051ce",
        "type": "ui_led",
        "z": "c1cfd9835acb2e31",
        "order": 5,
        "group": "7a1198fbe6345632",
        "width": "6",
        "height": "1",
        "label": "",
        "labelPlacement": "left",
        "labelAlignment": "left",
        "colorForValue": [
            {
                "color": "#11ff00",
                "value": "RUNNING",
                "valueType": "str"
            },
            {
                "color": "#fbff00",
                "value": "DOWNTIME",
                "valueType": "str"
            },
            {
                "color": "#ff0000",
                "value": "BREAKDOWN",
                "valueType": "str"
            }
        ],
        "allowColorForValueInMessage": false,
        "shape": "circle",
        "showGlow": true,
        "name": "",
        "x": 1250,
        "y": 140,
        "wires": []
    },
    {
        "id": "713c94107329a0de",
        "type": "ui_led",
        "z": "c1cfd9835acb2e31",
        "order": 1,
        "group": "aa0ad3153fa65903",
        "width": "2",
        "height": "1",
        "label": "",
        "labelPlacement": "left",
        "labelAlignment": "left",
        "colorForValue": [
            {
                "color": "#00ff00",
                "value": "true",
                "valueType": "bool"
            }
        ],
        "allowColorForValueInMessage": false,
        "shape": "circle",
        "showGlow": true,
        "name": "",
        "x": 310,
        "y": 660,
        "wires": []
    },
    {
        "id": "8bf272d6d0c18270",
        "type": "ui_led",
        "z": "c1cfd9835acb2e31",
        "order": 1,
        "group": "aa0ad3153fa65903",
        "width": "2",
        "height": "1",
        "label": "",
        "labelPlacement": "left",
        "labelAlignment": "left",
        "colorForValue": [
            {
                "color": "#ff9500",
                "value": "false",
                "valueType": "bool"
            }
        ],
        "allowColorForValueInMessage": false,
        "shape": "circle",
        "showGlow": true,
        "name": "",
        "x": 310,
        "y": 940,
        "wires": []
    },
    {
        "id": "694335fa354cd3c8",
        "type": "ui_switch",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "switch",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "passthru": true,
        "decouple": "false",
        "topic": "topic",
        "topicType": "msg",
        "style": "",
        "onvalue": "true",
        "onvalueType": "bool",
        "onicon": "",
        "oncolor": "",
        "offvalue": "false",
        "offvalueType": "bool",
        "officon": "",
        "offcolor": "",
        "animate": false,
        "className": "",
        "x": 190,
        "y": 660,
        "wires": [
            [
                "713c94107329a0de"
            ]
        ]
    },
    {
        "id": "77494a96d6ecf6d6",
        "type": "ui_switch",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "label": "switch",
        "tooltip": "",
        "group": "c65eda9f17231468",
        "order": 2,
        "width": 0,
        "height": 0,
        "passthru": true,
        "decouple": "false",
        "topic": "topic",
        "topicType": "msg",
        "style": "",
        "onvalue": "true",
        "onvalueType": "bool",
        "onicon": "",
        "oncolor": "",
        "offvalue": "false",
        "offvalueType": "bool",
        "officon": "",
        "offcolor": "",
        "animate": false,
        "className": "",
        "x": 190,
        "y": 940,
        "wires": [
            [
                "8bf272d6d0c18270"
            ]
        ]
    },
    {
        "id": "a7dfc66917643b04",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"reset\") {\n    msg.payload = msg.payload;\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 870,
        "y": 540,
        "wires": [
            [
                "db1b7b2ed1af747e"
            ]
        ]
    },
    {
        "id": "25c3693efe7fe25f",
        "type": "function-npm",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "func": "if (msg.topic === \"Caution !!\") {\n    msg.payload = \"Dashboard telah berhasil di reset\";\n    node.send(msg);\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 1190,
        "y": 540,
        "wires": [
            [
                "c180f831ebacd094"
            ]
        ]
    },
    {
        "id": "c180f831ebacd094",
        "type": "ui_toast",
        "z": "c1cfd9835acb2e31",
        "position": "top right",
        "displayTime": "3",
        "highlight": "",
        "sendall": true,
        "outputs": 0,
        "ok": "OK",
        "cancel": "",
        "raw": false,
        "className": "",
        "topic": "",
        "name": "",
        "x": 1430,
        "y": 640,
        "wires": []
    },
    {
        "id": "db1b7b2ed1af747e",
        "type": "ui_button",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "group": "c65eda9f17231468",
        "order": 3,
        "width": 0,
        "height": 0,
        "passthru": true,
        "label": "Reset Data",
        "tooltip": "",
        "color": "",
        "bgcolor": "",
        "className": "",
        "icon": "save",
        "payload": "",
        "payloadType": "date",
        "topic": "Caution !!",
        "topicType": "str",
        "x": 1030,
        "y": 540,
        "wires": [
            [
                "25c3693efe7fe25f"
            ]
        ]
    },
    {
        "id": "157d527fecce6420",
        "type": "trigger",
        "z": "c1cfd9835acb2e31",
        "name": "",
        "op1": "",
        "op2": "",
        "op1type": "pay",
        "op2type": "pay",
        "duration": "10",
        "extend": false,
        "overrideDelay": false,
        "units": "ms",
        "reset": "",
        "bytopic": "all",
        "topic": "topic",
        "outputs": 1,
        "x": 350,
        "y": 740,
        "wires": [
            [
                "ecd4be7e28a4f584"
            ]
        ]
    },
    {
        "id": "6e7f7321ab39cec7",
        "type": "ui_spacer",
        "z": "c1cfd9835acb2e31",
        "name": "spacer",
        "group": "29986c92d065db26",
        "order": 3,
        "width": "5",
        "height": "1"
    },
    {
        "id": "2456e80f23d934af",
        "type": "ui_spacer",
        "z": "c1cfd9835acb2e31",
        "name": "spacer",
        "group": "29986c92d065db26",
        "order": 6,
        "width": "5",
        "height": "1"
    },
    {
        "id": "173edc6a6fc4a24c",
        "type": "ui_spacer",
        "z": "c1cfd9835acb2e31",
        "name": "spacer",
        "group": "80e2142f0aa4abd6",
        "order": 3,
        "width": "6",
        "height": "1"
    },
    {
        "id": "20ba6d85a9e00216",
        "type": "ui_spacer",
        "z": "c1cfd9835acb2e31",
        "name": "spacer",
        "group": "80e2142f0aa4abd6",
        "order": 6,
        "width": "6",
        "height": "1"
    },
    {
        "id": "1600b133f9b8de2b",
        "type": "ui_spacer",
        "z": "c1cfd9835acb2e31",
        "name": "spacer",
        "group": "80e2142f0aa4abd6",
        "order": 9,
        "width": "6",
        "height": "1"
    },
    {
        "id": "7a1198fbe6345632",
        "type": "ui_group",
        "name": "Status Line",
        "tab": "b469ad13b57dfbb2",
        "order": 3,
        "disp": true,
        "width": 6,
        "collapse": false,
        "className": ""
    },
    {
        "id": "254ff0e8700612df",
        "type": "ui_group",
        "name": "Tanggal/Waktu",
        "tab": "b469ad13b57dfbb2",
        "order": 1,
        "disp": true,
        "width": 4,
        "collapse": false,
        "className": ""
    },
    {
        "id": "29986c92d065db26",
        "type": "ui_group",
        "name": "Waktu Line",
        "tab": "b469ad13b57dfbb2",
        "order": 4,
        "disp": true,
        "width": "5",
        "collapse": false,
        "className": ""
    },
    {
        "id": "80e2142f0aa4abd6",
        "type": "ui_group",
        "name": "Achievement Aktual",
        "tab": "b469ad13b57dfbb2",
        "order": 6,
        "disp": true,
        "width": "6",
        "collapse": false,
        "className": ""
    },
    {
        "id": "3323f7416b9a5747",
        "type": "ui_group",
        "name": "Data Produk",
        "tab": "2c021190d498ee99",
        "order": 1,
        "disp": true,
        "width": "8",
        "collapse": false,
        "className": ""
    },
    {
        "id": "e34bc21bc9269937",
        "type": "ui_group",
        "name": "Data Produksi",
        "tab": "b469ad13b57dfbb2",
        "order": 2,
        "disp": true,
        "width": "7",
        "collapse": false,
        "className": ""
    },
    {
        "id": "aa0ad3153fa65903",
        "type": "ui_group",
        "name": "Control",
        "tab": "b469ad13b57dfbb2",
        "order": 5,
        "disp": true,
        "width": "4",
        "collapse": false,
        "className": ""
    },
    {
        "id": "c65eda9f17231468",
        "type": "ui_group",
        "name": "Tidak untuk diganggu",
        "tab": "57a3f10ee3f9036a",
        "order": 1,
        "disp": true,
        "width": "6",
        "collapse": false,
        "className": ""
    },
    {
        "id": "6db947571d49f1a7",
        "type": "ui_group",
        "name": "Performance",
        "tab": "b469ad13b57dfbb2",
        "order": 9,
        "disp": true,
        "width": "4",
        "collapse": false,
        "className": ""
    },
    {
        "id": "eb41c3ec879e0163",
        "type": "s7 endpoint",
        "transport": "iso-on-tcp",
        "address": "192.168.0.3",
        "port": "102",
        "rack": "0",
        "slot": "2",
        "localtsaphi": "02",
        "localtsaplo": "00",
        "remotetsaphi": "03",
        "remotetsaplo": "00",
        "connmode": "tsap",
        "adapter": "",
        "busaddr": "2",
        "cycletime": "50",
        "timeout": "1000",
        "name": "PLC Logo 8",
        "vartable": [
            {
                "addr": "DB1,X1024.0",
                "name": "On/Off"
            },
            {
                "addr": "DB1,X1024.2",
                "name": "Reset"
            },
            {
                "addr": "DB1,X1024.3",
                "name": "Sensor Input"
            },
            {
                "addr": "DB1,X1024.4",
                "name": "Sensor Output"
            },
            {
                "addr": "DB1,X1104.0",
                "name": "M1"
            },
            {
                "addr": "DB1,X1104.1",
                "name": "M2"
            },
            {
                "addr": "DB1,X1104.2",
                "name": "M3"
            },
            {
                "addr": "DB1,X1104.3",
                "name": "M4"
            }
        ]
    },
    {
        "id": "ba287d2c91a9859f",
        "type": "ui_group",
        "name": "Achievement per waktu",
        "tab": "b469ad13b57dfbb2",
        "order": 7,
        "disp": true,
        "width": "8",
        "collapse": false,
        "className": ""
    },
    {
        "id": "3db337b444e5d026",
        "type": "gauth",
        "name": "node-red@digitalisasi-ria-14.iam.gserviceaccount.com"
    },
    {
        "id": "b469ad13b57dfbb2",
        "type": "ui_tab",
        "name": "Real Time Line Performance - Indofood Ice Cream",
        "icon": "dashboard",
        "order": 1,
        "disabled": false,
        "hidden": false
    },
    {
        "id": "2c021190d498ee99",
        "type": "ui_tab",
        "name": "Data Produksi",
        "icon": "dashboard",
        "order": 2,
        "disabled": false,
        "hidden": false
    },
    {
        "id": "57a3f10ee3f9036a",
        "type": "ui_tab",
        "name": "Hide",
        "icon": "dashboard",
        "disabled": false,
        "hidden": true
    }
]
