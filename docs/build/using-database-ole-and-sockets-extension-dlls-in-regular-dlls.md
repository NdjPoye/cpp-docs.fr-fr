---
title: "Utilisation de DLL d&#39;extension de type base de donn&#233;es, OLE et sockets dans des DLL normales | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), extension"
  - "DLL (C++), initialiser"
  - "DLL (C++), normales"
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Utilisation de DLL d&#39;extension de type base de donn&#233;es, OLE et sockets dans des DLL normales
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous utilisez une DLL d'extension à partir d'une DLL normale et que la DLL d'extension n'est pas raccordée à la chaîne d'objets **CDynLinkLibrary** de la DLL normale, vous risquez de rencontrer un ou plusieurs problèmes connexes.  Comme les versions Debug des DLL prenant en charge les ressources base de données, OLE et sockets MFC sont implémentées en tant que DLL d'extension, vous pouvez rencontrer des problèmes similaires si vous employez ces fonctionnalités MFC, même si vous n'utilisez pas explicitement vos propres DLL d'extension.  Voici quelques symptômes à prendre en compte :  
  
-   Lorsque vous essayez de désérialiser un objet d'un type de classe défini dans la DLL d'extension, le message "Avertissement : Impossible de charger CYourClass à partir de l'archive.  Classe non définie." apparaît dans la fenêtre de débogage TRACE et la sérialisation de l'objet échoue.  
  
-   Une exception indiquant que la classe est incorrecte peut être levée.  
  
-   Les ressources stockées dans la DLL d'extension ne se chargent pas car `AfxFindResourceHandle` retourne **NULL** ou un handle de ressource incorrect.  
  
-   `DllGetClassObject`, `DllCanUnloadNow` et les fonctions membres `UpdateRegistry`, `Revoke`, `RevokeAll` et `RegisterAll` de `COleObjectFactory` ne réussissent pas à trouver une fabrique de classe définie dans la DLL d'extension.  
  
-   `AfxDoForAllClasses` ne fonctionne pas pour les classes dans la DLL d'extension.  
  
-   Les ressources base de données, sockets ou OLE MFC standard ne se chargent pas.  Par exemple, **AfxLoadString**\(**AFX\_IDP\_SQL\_CONNECT\_FAIL**\) retourne une chaîne vide, même quand la DLL normale utilise correctement les classes de base de données MFC.  
  
 La solution de ces problèmes consiste à créer et à exporter une fonction d'initialisation dans la DLL d'extension qui crée un objet **CDynLinkLibrary**.  Appelez cette fonction d'initialisation une seule fois à partir de chaque DLL normale utilisant la DLL d'extension.  
  
## Prise en charge des ressources OLE MFC, base de données MFC \(ou DAO\) ou sockets MFC  
 Si vous intégrez une prise en charge des ressources OLE MFC, base de données MFC \(ou DAO\) ou sockets MFC dans la DLL normale, les DLL d'extension de débogage MFC  MFCOxxD.dll, MFCDxxD.dll et MFCNxxD.dll \(où xx correspond au numéro de version\) sont, respectivement, liées de façon automatique.  Vous devez appeler une fonction d'initialisation prédéfinie pour chacune de ces DLL que vous utilisez.  
  
 Pour la prise en charge de base de données, ajoutez un appel à `AfxDbInitModule` à la fonction `CWinApp::InitInstance` de la DLL normale.  Vérifiez que cet appel se produit avant tout appel de classe de base ou tout ajout de code qui accède à MFCDxxD.dll.  Cette fonction ne prend pas de paramètres et retourne void.  
  
 Pour la prise en charge d'OLE, ajoutez un appel à `AfxOleInitModule` à la fonction `CWinApp::InitInstance` de la DLL normale.  Notez que la fonction **InitInstance** de **COleControlModule** appelle déjà `AfxOleInitModule` ; si vous générez donc un contrôle OLE et utilisez `COleControlModule`, vous ne devez pas ajouter cet appel à `AfxOleInitModule`.  
  
 Pour la prise en charge des sockets, ajoutez un appel à `AfxNetInitModule` à la fonction `CWinApp::InitInstance` de la DLL normale.  
  
 Notez que les versions Release des applications et des DLL MFC n'utilisent pas des DLL séparées pour la prise en charge des ressources base de données, sockets et OLE.  Cependant, il n'y a aucun risque à appeler ces fonctions d'initialisation en mode Release.  
  
## Objets CDynLinkLibrary  
 Pendant chacune des opérations mentionnées au début de cette rubrique, les MFC doivent rechercher une valeur ou un objet particulier.  Par exemple, pendant la désérialisation, les MFC doivent parcourir toutes les classes d'exécution disponibles afin d'essayer de faire correspondre des objets de l'archive avec leur propre classe d'exécution.  
  
 Dans le cadre de ces recherches, les MFC analysent toutes les DLL d'extension utilisées en parcourant une chaîne d'objets **CDynLinkLibrary**.  Les objets **CDynLinkLibrary** s'attachent automatiquement à une chaîne pendant leur construction et sont créés par chaque DLL d'extension, à tour de rôle, pendant l'initialisation.  En outre, chaque module \(application ou DLL normale\) possède sa propre chaîne d'objets **CDynLinkLibrary**.  
  
 Pour qu'une DLL d'extension puisse être raccordée à une chaîne **CDynLinkLibrary**, elle doit créer un objet **CDynLinkLibrary** dans le contexte de chaque module utilisant la DLL d'extension.  Par conséquent, si vous comptez utiliser une DLL d'extension à partir de DLL normales, cette DLL doit fournir une fonction d'initialisation exportée qui crée un objet **CDynLinkLibrary**.  Chaque DLL normale utilisant la DLL d'extension doit appeler la fonction d'initialisation exportée.  
  
 Si vous comptez utiliser une DLL d'extension seulement à partir d'une application MFC \(.exe\) et jamais à partir d'une DLL normale, il suffit alors de créer l'objet **CDynLinkLibrary** dans la fonction `DllMain` de la DLL d'extension.  C'est ce que fait le code de la DLL d'extension de l'Assistant DLL MFC.  Lors du chargement d'une DLL d'extension de manière implicite, `DllMain` se charge et s'exécute avant même que l'application démarre.  Toutes les créations **CDynLinkLibrary** sont raccordées à une chaîne par défaut que la DLL MFC réserve pour une application MFC.  
  
 Notez qu'il est déconseillé d'avoir plusieurs objets **CDynLinkLibrary** d'une même DLL d'extension dans la même chaîne, particulièrement si la DLL d'extension sera déchargée de manière dynamique de la mémoire.  N'appelez pas la fonction d'initialisation plus d'une fois à partir du même module.  
  
## Exemple de code  
 Cet exemple de code suppose que la DLL normale est liée de manière implicite à la DLL d'extension.  Cette opération est réalisée par l'établissement d'une liaison avec la bibliothèque d'importation \(.lib\) de la DLL d'extension lors de la génération de la DLL normale.  
  
 Les lignes suivantes doivent figurer dans la source de la DLL d'extension :  
  
```  
// YourExtDLL.cpp:  
  
// standard MFC extension DLL routines  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
    if (dwReason == DLL_PROCESS_ATTACH)  
    {  
        // extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 Veillez à exporter la fonction **InitYourExtDLL**.  Cette opération peut être effectuée à l'aide de **\_\_declspec\(dllexport\)** ou dans le fichier .def de la DLL, de la manière suivante :  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 Ajoutez un appel au membre `InitInstance` de l'objet dérivé de `CWinApp` dans chaque DLL normale utilisant la DLL d'extension :  
  
```  
// YourRegularDLL.cpp:  
  
class CYourRegularDLL : public CWinApp  
{  
public:  
    virtual BOOL InitInstance(); // Initialization  
    virtual int ExitInstance();  // Termination  
  
    // nothing special for the constructor  
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }  
};  
  
BOOL CYourRegularDLL::InitInstance()  
{  
    // any DLL initialization goes here  
    TRACE0("YOUR regular DLL initializing\n");  
  
    // wire any extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### Que voulez\-vous faire ?  
  
-   [Initialiser une DLL d'extension](../build/initializing-extension-dlls.md)  
  
-   [Initialiser des DLL normales](../build/initializing-regular-dlls.md)  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [DLL d'extension](../build/extension-dlls.md)  
  
-   [DLL normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Utilisation de MFC dans le cadre d'une DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [Version DLL de MFC](../mfc/tn033-dll-version-of-mfc.md)  
  
## Voir aussi  
 [DLL d'extension](../build/extension-dlls.md)