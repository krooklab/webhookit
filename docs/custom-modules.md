
# Creating custom modules

in lib/modules


    exports.run = function(params, cb) {
	
    	console.log("My module !");
    	console.log(params);
	
    	// You can return anything
    	cb({out: ["ceci", 354, "une", "liste"]});
	
    };

    exports.definition = {
      "name": "myModule",
    	"category": "Templating",
       "container": {
    		"icon": "/images/icons/script_edit.png",
          "xtype": "WireIt.MyModuleContainer",
    		"title": "Liquid",
    		"fields": [
    			{"type": "text", "name": "template", "wirable": false }
    		],
    		"terminals": [
    			{"name": "in", "direction": [0,-1], "offsetPosition": [82,-15], "ddConfig": {
                 "type": "input",
                 "allowedTypes": ["output"]
              },
              "nMaxWires": 1
             },
    		   {"name": "out", "direction": [0,1], "offsetPosition": {"left": 86, "bottom": -15}, "ddConfig": {
                 "type": "output",
                 "allowedTypes": ["input"]
              }
             }
    	   ]
       }
    };