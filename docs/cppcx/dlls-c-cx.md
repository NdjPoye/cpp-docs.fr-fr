---
title: "DLL (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 21
---
# DLL (C++/CX)
Vous pouvez utiliser Visual Studio pour créer une DLL Win32 standard ou une DLL de composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] pouvant être utilisée par les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]. Une DLL standard créée à l'aide d'une version de Visual Studio ou d'une version du compilateur Visual C\+\+ antérieure à [!INCLUDE[vs_dev11_long](../cppcx/includes/vs-dev11-long-md.md)] peut ne pas se charger correctement dans une application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] et échouer au test de vérification d'application dans [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)].  
  
## DLL de composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]  
 Dans la plupart des cas, si vous souhaitez créer une DLL à utiliser dans une application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], créez\-la en tant que composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] à l'aide du modèle de projet du même nom. Vous pouvez créer un projet de composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] pour les DLL qui ont des types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] publics ou privés. Les composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] sont accessibles à partir des applications écrites dans n'importe quel langage compatible [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Par défaut, les paramètres du compilateur d'un projet de composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] utilisent le commutateur **\/ZW**. Un fichier .winmd doit avoir le même nom que l'espace de noms racine. Par exemple, une classe nommée A.B.C.MyClass peut être instanciée uniquement si elle est définie dans un fichier de métadonnées nommé A.winmd, A.B.winmd ou A.B.C.winmd. Il n'est pas requis que le nom de la DLL corresponde au nom du fichier .winmd.  
  
 Pour plus d'informations, consultez [Création de composants Windows Runtime en C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md).  
  
#### Référencement d'un fichier binaire de composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] tiers dans votre projet  
  
1.  Ouvrez le menu contextuel du projet qui utilisera la DLL puis choisissez **Propriétés**. Dans la page **Propriétés communes**, choisissez le bouton **Ajouter une nouvelle référence**.  
  
2.  Un composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] se compose d'un fichier DLL et d'un fichier .winmd qui contient les métadonnées. En général, ces fichiers se trouvent dans le même répertoire. Dans le volet gauche de la boîte de dialogue **Ajouter une référence**, choisissez le bouton **Parcourir** puis accédez à l'emplacement de la DLL et de son fichier .winmd. Pour plus d’informations, consultez [Didacticiel : création et utilisation de kits de développement logiciel d’extension](http://msdn.microsoft.com/fr-fr/001e2fca-3d56-43ab-a5e0-0561d085679f).  
  
## DLL standard  
 Vous pouvez créer une DLL standard pour le code C\+\+ qui n'utilise ou ne produit pas de types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] publics et l'utilise à partir d'une application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]. Si vous souhaitez juste migrer une DLL existante, utilisez le type de projet de la DLL [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] pour la compiler dans cette version de Visual Studio, sans convertir le code en un projet Composant Windows Runtime. En utilisant la procédure suivante, la DLL sera déployée à côté de l'exécutable de votre application dans le package .appx.  
  
#### Pour créer une DLL standard dans Visual Studio  
  
1.  Dans la barre de menus, sélectionnez **Fichier**, **Nouveau**, **Projet**, puis sélectionnez le modèle DLL [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)].  
  
2.  Entrez un nom pour le projet, puis choisissez le bouton **OK**.  
  
3.  Ajoutez le code. Veillez à utiliser `__declspec(dllexport)` pour les fonctions que vous prévoyez d'exporter, par exemple `__declspec(dllexport) Add(int I, in j);`  
  
4.  Ajoutez `#include winapifamily.h` pour inclure ce fichier d'en\-tête du Kit de développement logiciel pour les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] et définissez la macro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
#### Référencement d'un projet DLL standard à partir de la même solution  
  
1.  Ouvrez le menu contextuel du projet qui utilisera la DLL puis choisissez **Propriétés**. Dans la page **Propriétés communes**, choisissez le bouton **Ajouter une nouvelle référence**.  
  
2.  Dans le volet gauche, sélectionnez **Solution**, puis activez la case à cocher appropriée dans le volet droit.  
  
3.  Dans vos fichiers de code source, ajoutez une instruction `#include` pour le fichier d'en\-tête de DLL selon vos besoins.  
  
#### Référencement d'un fichier binaire de DLL standard  
  
1.  Copiez le fichier DLL, le fichier .lib et le fichier d'en\-tête, puis collez\-les dans un emplacement connu, par exemple dans votre dossier de projet actif.  
  
2.  Ouvrez le menu contextuel du projet qui utilisera la DLL puis choisissez **Propriétés**. Dans la page **Propriétés de configuration**, **Éditeur de liens**, **Entrée**, ajoutez le fichier .lib comme dépendance.  
  
3.  Dans vos fichiers de code source, ajoutez une instruction `#include` pour le fichier d'en\-tête de DLL selon vos besoins.  
  
#### Migration d'une DLL Win32 existante pour la compatibilité des applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]  
  
1.  Créez un projet de type DLL [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] et ajoutez votre code source existant à celui\-ci.  
  
2.  Ajoutez `#include winapifamily.h` pour inclure ce fichier d'en\-tête du Kit de développement logiciel pour les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] et définissez la macro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
3.  Dans vos fichiers de code source, ajoutez une instruction `#include` pour le fichier d'en\-tête de DLL selon vos besoins.  
  
## Voir aussi  
 [\(NOTINBUILD\) Rubriques avancées](http://msdn.microsoft.com/fr-fr/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)