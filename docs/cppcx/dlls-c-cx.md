---
title: DLL (C + c++ / CX) | Documents Microsoft
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a759541dd31121f12283f9b2b0c5b468da477554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="dlls-ccx"></a>DLL (C++/CX)
Vous pouvez utiliser Visual Studio pour créer une DLL Win32 standard ou un composant Windows Runtime DLL qui peut être utilisé par les applications de plateforme Windows universelle. Une DLL standard qui a été créée à l’aide d’une version de Visual Studio ou le compilateur Visual C++ antérieure à Visual Studio 2012 peut ne pas se charger correctement dans une application de plateforme Windows universelle et peut ne pas passer le test de vérification d’application dans le [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)].  
  
## <a name="windows-runtime-component-dlls"></a>DLL de composants Windows Runtime  
 Dans la plupart des cas, lorsque vous souhaitez créer une DLL à utiliser dans une application de plateforme Windows universelle, créez-le en tant qu’un composant Windows Runtime à l’aide du modèle de projet du même nom. Vous pouvez créer un projet de composant Windows Runtime pour les DLL qui ont des types Windows Runtime publics ou privés. Un composant Windows Runtime est accessible à partir d’applications qui sont écrites dans n’importe quel langage compatible avec Windows Runtime. Par défaut, les paramètres de compilateur pour un composant Windows Runtime de projets Utilisez la **/ZW** basculer. Un fichier .winmd doit avoir le même nom que l'espace de noms racine. Par exemple, une classe nommée A.B.C.MyClass peut être instanciée uniquement si elle est définie dans un fichier de métadonnées nommé A.winmd, A.B.winmd ou A.B.C.winmd. Il n'est pas requis que le nom de la DLL corresponde au nom du fichier .winmd.  
  
 Pour plus d'informations, consultez [Creating Windows Runtime Components in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
#### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>Pour faire référence à un composant de Windows Runtime tiers binaire dans votre projet  
  
1.  Ouvrez le menu contextuel du projet qui utilisera la DLL puis choisissez **Propriétés**. Dans la page **Propriétés communes** , choisissez le bouton **Ajouter une nouvelle référence** .  
  
2.  Un composant Windows Runtime se compose d’un fichier DLL et un fichier .winmd qui contient les métadonnées. En général, ces fichiers se trouvent dans le même répertoire. Dans le volet gauche de la boîte de dialogue **Ajouter une référence** , choisissez le bouton **Parcourir** puis accédez à l'emplacement de la DLL et de son fichier .winmd. Pour plus d’informations, consultez [Didacticiel : création et utilisation de kits de développement logiciel d’extension](http://msdn.microsoft.com/en-us/001e2fca-3d56-43ab-a5e0-0561d085679f).  
  
## <a name="standard-dlls"></a>DLL standard  
 Vous pouvez créer une DLL standard pour le code C++ qui ne consomment ou produisent des types Windows Runtime publics et consommer à partir d’une application de plateforme Windows universelle. Utilisez le type de projet de DLL de plateforme Windows universelle lorsque vous souhaitez juste migrer une DLL existante pour la compiler dans cette version de Visual Studio, sans convertir le code à un projet de composant Windows Runtime. En utilisant la procédure suivante, la DLL sera déployée à côté de l'exécutable de votre application dans le package .appx.  
  
#### <a name="to-create-a-standard-dll-in-visual-studio"></a>Pour créer une DLL standard dans Visual Studio  
  
1.  Dans la barre de menus, choisissez **fichier**, **nouveau**, **projet**, puis sélectionnez le modèle de la DLL de plateforme Windows universelle.  
  
2.  Entrez un nom pour le projet, puis choisissez le bouton **OK** .  
  
3.  Ajoutez le code. Veillez à utiliser `__declspec(dllexport)` pour les fonctions que vous prévoyez d'exporter, par exemple `__declspec(dllexport) Add(int I, in j);`  
  
4.  Ajouter `#include winapifamily.h` pour inclure ce fichier d’en-tête à partir du Kit de développement pour les applications de plateforme Windows universelle et de définir la macro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
#### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>Référencement d'un projet DLL standard à partir de la même solution  
  
1.  Ouvrez le menu contextuel du projet qui utilisera la DLL puis choisissez **Propriétés**. Dans la page **Propriétés communes** , choisissez le bouton **Ajouter une nouvelle référence** .  
  
2.  Dans le volet gauche, sélectionnez **Solution**, puis activez la case à cocher appropriée dans le volet droit.  
  
3.  Dans vos fichiers de code source, ajoutez une instruction `#include` pour le fichier d'en-tête de DLL selon vos besoins.  
  
#### <a name="to-reference-a-standard-dll-binary"></a>Référencement d'un fichier binaire de DLL standard  
  
1.  Copiez le fichier DLL, le fichier .lib et le fichier d'en-tête, puis collez-les dans un emplacement connu, par exemple dans votre dossier de projet actif.  
  
2.  Ouvrez le menu contextuel du projet qui utilisera la DLL puis choisissez **Propriétés**. Dans la page **Propriétés de configuration**, **Éditeur de liens**, **Entrée** , ajoutez le fichier .lib comme dépendance.  
  
3.  Dans vos fichiers de code source, ajoutez une instruction `#include` pour le fichier d'en-tête de DLL selon vos besoins.  
  
#### <a name="to-migrate-an-existing-win32-dll-for-universal-windows-platform-app-compatibility"></a>Pour migrer une DLL Win32 existante pour la compatibilité des applications de plateforme Windows universelle  
  
1.  Créez un projet du type de DLL de plateforme Windows universelle et ajoutez votre code source existant à celui-ci.  
  
2.  Ajouter `#include winapifamily.h` pour inclure ce fichier d’en-tête à partir du Kit de développement pour les applications de plateforme Windows universelle et de définir la macro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
3.  Dans vos fichiers de code source, ajoutez une instruction `#include` pour le fichier d'en-tête de DLL selon vos besoins.  
  

