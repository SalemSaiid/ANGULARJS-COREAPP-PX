# ANGULARJS-COREAPP-PX (structure modules)

<strong>app/i18n :</strong> contient les fichiers de traduction <br />
<strong>app/main :</strong> contient le module principal (Bootstrap) avec ces ressources <br />
<strong>app/app.config.js :</strong> Fichier de configuration du module de démarrage (Bootstrap) <br />
<strong>assets :</strong> contient les assets et les plugins externes <br />

![alt tag](http://s22.postimg.org/8hgtavgy9/structure.png) <br><br>

<strong>Création d'un module</strong><br>
<br>
<strong>Création de l'arborescence</strong> <br>
Il suffit de créer sous app/modules un dossier avec le nom de votre nouveau module (exp "sample") puis créer les dossiers "controllers, views, services" selon votre besoin :<br>
![alt tag](http://s16.postimg.org/wkyt3gzbp/module.png) <br>

<strong>Configuration du module</strong><br>
Sous app/modules/ nomModule /nomModule.config.js : <br>
```

/**
 * Sample Module Configuration
 */

ModuleFactory.createModule({
    module : 'sample', // Name of the module
    dependencies : [], // Dependency injection
    states : [
        {
            name: 'sample', // State Name
            url: '/sample', // State URL
            templateUrl: 'index.html', // Template (it can be URL under 'app/modules/YOUR_MODULE_NAME/views/' or simple HTML code)
            abstract: true // true if your state is just a layout / container
        },
        {
            name: 'sample.test',
            url: '/test',
            controllers: ['test1Controller.js', 'test2Controller.js'], // List of controllers under 'app/modules/YOUR_MODULE_NAME/controllers/'
            views: {
                "view1": {
                    controller: "Test1Controller",
                    templateUrl: "app/modules/sample/views/view1.html" 
                },
                "view2": {
                    templateUrl: "app/modules/sample/views/view2.html" 
                }
            }
        }
    ]
});

```
