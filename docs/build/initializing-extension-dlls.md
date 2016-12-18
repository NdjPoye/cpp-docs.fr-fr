---
title: "Initialisation de DLL d&#39;extension | Microsoft Docs"
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
  - "DLL d'extension (C++), initialiser"
  - "initialiser les DLL"
ms.assetid: 08ad0381-3808-4bea-a93c-c9ba62496543
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Initialisation de DLL d&#39;extension
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la mesure où les DLL d'extension ne possèdent pas d'objet dérivé de `CWinApp` \(contrairement aux DLL normales\), vous devez ajouter le code d'initialisation et d'arrêt à la fonction `DllMain` générée par l'Assistant DLL MFC.  
  
 L'Assistant fournit le code suivant pour les DLL d'extension.  Dans le code, `PROJNAME` est un espace réservé pour le nom du projet.  
  
```  
#include "stdafx.h"  
#include <afxdllx.h>  
  
#ifdef _DEBUG  
#define new DEBUG_NEW  
#undef THIS_FILE  
static char THIS_FILE[] = __FILE__;  
#endif  
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      TRACE0("PROJNAME.DLL Initializing!\n");  
  
      // Extension DLL one-time initialization  
      AfxInitExtensionModule(PROJNAMEDLL,   
                                 hInstance);  
  
      // Insert this DLL into the resource chain  
      new CDynLinkLibrary(Dll3DLL);  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      TRACE0("PROJNAME.DLL Terminating!\n");  
   }  
   return 1;   // ok  
}  
```  
  
 La création d'un nouvel objet **CDynLinkLibrary** pendant l'initialisation permet à la DLL d'extension d'exporter des ressources ou des objets `CRuntimeClass` vers l'application cliente.  
  
 Si vous comptez utiliser la DLL d'extension à partir d'une ou plusieurs DLL normales, vous devez exporter une fonction d'initialisation qui crée un objet **CDynLinkLibrary**.  Cette fonction doit être appelée à partir de chaque DLL normale utilisant la DLL d'extension.  La fonction membre `InitInstance` de l'objet dérivé de `CWinApp` de la DLL normale est un emplacement approprié pour appeler cette fonction d'initialisation avant d'utiliser l'une des fonctions ou classes exportées de la DLL d'extension.  
  
 Dans le `DllMain` généré par l'Assistant DLL MFC, l'appel de `AfxInitExtensionModule` capture les classes d'exécution du module \(structures `CRuntimeClass`\) ainsi que ses fabriques d'objets \(objets `COleObjectFactory`\) pour les utiliser lors de la création de l'objet **CDynLinkLibrary**.  Vous devez vérifier la valeur de retour de `AfxInitExtensionModule` ; si une valeur zéro est retournée à partir de `AfxInitExtensionModule`, retournez zéro à partir de votre fonction `DllMain`.  
  
 Si vous envisagez que la DLL d'extension soit liée de manière explicite à un exécutable \(ce qui signifie que l'exécutable appelle `AfxLoadLibrary` pour se lier à la DLL\), vous devez ajouter un appel à `AfxTermExtensionModule` sur **DLL\_PROCESS\_DETACH**.  Cette fonction permet aux MFC de nettoyer la DLL d'extension chaque fois qu'un processus se détache de la DLL d'extension \(ce qui se produit lors de la sortie du processus ou quand la DLL est déchargée à la suite d'un appel à `AfxFreeLibrary`\).  Si la DLL d'extension est liée de manière implicite à l'application, l'appel à `AfxTermExtensionModule` n'est pas nécessaire.  
  
 Les applications qui se lient de manière explicite aux DLL d'extension doivent appeler **AfxTermExtensionModule** lorsqu'elles libèrent la DLL.  Elles doivent également utiliser `AfxLoadLibrary` et `AfxFreeLibrary` \(à la place des fonctions Win32 **LoadLibrary** et **FreeLibrary**\) si l'application utilise plusieurs threads.  L'utilisation de `AfxLoadLibrary` et de `AfxFreeLibrary` fait en sorte que le code de démarrage et d'arrêt qui s'exécute lors du chargement et du déchargement de la DLL d'extension n'altère pas l'état global des MFC.  
  
 Dans la mesure où MFCx0.dll est complètement initialisée au moment où la fonction `DllMain` est appelée, vous pouvez allouer de la mémoire et appeler des fonctions MFC dans `DllMain` \(contrairement à la version 16 bits des MFC\).  
  
 Les DLL d'extension peuvent prendre en charge le multithreading en gérant les cas **DLL\_THREAD\_ATTACH** et **DLL\_THREAD\_DETACH** dans la fonction `DllMain`.  Ces cas sont passés à `DllMain` lorsque les threads s'attachent et se détachent de la DLL.  L'appel à [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) lors de l'attachement d'une DLL permet à celle\-ci de mettre en œuvre des index de stockage local des threads pour chaque thread attaché à la DLL.  
  
 Notez que le fichier d'en\-tête Afxdllx.h contient des définitions spéciales pour les structures utilisées dans les DLL d'extension, comme la définition de `AFX_EXTENSION_MODULE` et de **CDynLinkLibrary**.  Vous devez inclure ce fichier d'en\-tête dans la DLL d'extension.  
  
> [!NOTE]
>  Il est important de pas définir ni annuler la définition des macros \_AFX\_NO\_XXX dans Stdafx.h.  Pour plus d'informations, consultez l'article de la Base de connaissances \(page éventuellement en anglais\) « PRB: Problems Occur When Defining \_AFX\_NO\_XXX » \(Q140751\).  Vous trouverez les articles de la Base de connaissances dans la bibliothèque MSDN ou à l'adresse [http:\/\/search.support.microsoft.com\/](http://search.support.microsoft.com/).  
  
 Un exemple de fonction d'initialisation qui gère le multithreading est inclus dans [Utilisation du stockage local des threads dans une bibliothèque de liens dynamiques](http://msdn.microsoft.com/library/windows/desktop/ms686997) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  Notez que cet exemple contient une fonction de point d'entrée appelée **LibMain**, mais vous devez nommer cette fonction `DllMain` afin qu'elle fonctionne avec les MFC et les bibliothèques runtime du C.  
  
 L'exemple MFC [DLLHUSK](http://msdn.microsoft.com/fr-fr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) illustre l'utilisation des fonctions d'initialisation.  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser des DLL normales](../build/initializing-regular-dlls.md)  
  
-   [Initialiser des DLL non\-MFC](../build/initializing-non-mfc-dlls.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Comportement de la bibliothèque Runtime C et DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [Utilisation de DLL d'extension de type base de données, OLE et sockets dans des DLL normales](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt34" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>La spécification de fonction pour DllMain \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt35" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Fonction de point d'entrée de bibliothèque de liens dynamiques \(Kit de développement logiciel Windows\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## Voir aussi  
 [Initialisation d'une DLL](../build/initializing-a-dll.md)