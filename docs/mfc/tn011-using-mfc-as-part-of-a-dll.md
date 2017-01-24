---
title: "TN011&#160;: utilisation de MFC dans le cadre d&#39;une DLL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_USRDLL (symbole)"
  - "DLL (C++), lier"
  - "DLL MFC (C++), lier des DLL standard aux MFC"
  - "TN011"
  - "USRDLL, commutateurs de compilation"
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
caps.latest.revision: 20
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN011&#160;: utilisation de MFC dans le cadre d&#39;une DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette note décrit les DLL ordinaires, ce qui vous permet d'utiliser la bibliothèque MFC dans une bibliothèque de liens dynamiques Windows \(DLL\).  Cela suppose que vous connaissez les DLL windows et comment les créer.  Pour plus d'informations sur les DLL d'extension MFC, avec lesquels vous pouvez créer des extensions à la bibliothèque MFC, consultez [Version de DLL de MFC](../mfc/tn033-dll-version-of-mfc.md).  
  
## Interfaces DLL  
 Les DLL normaes supposent que les interfaces entre l'application et la DLL sont spécifiées dans les fonctions C\-similaires ou les classes explicitement exportées.  Les interfaces de classe de MFC ne peuvent pas être exportées.  
  
 Si une DLL et une application veulent utiliser MFC, elles peuvent toutes deux soit utiliser la version partagée des bibliothèques MFC ou utiliser un lien statiquement vers une copie des bibliothèques.  L'application et la DLL peuvent toutes deux utiliser l'une des versions standard de la bibliothèque MFC.  
  
 Les DLL normales ont plusieurs avantages :  
  
-   Une application qui utilise la DLL ne doit pas utiliser MFC et ne doit pas nécessairement être une application Visual C\+\+.  
  
-   Avec les DLL standard qui lient statiquement à MFC, la taille de la DLL dépend uniquement de MFC et des routines de service du runtime C utilisés et liés.  
  
-   Avec les DLL standard qui lient dynamiquement à MFC, les gains en mémoire dus à l'utilisation la version partagée de MFC peuvent être significatifs.  Toutefois, vous devez distribuer les DLL partagées, Mfc*\<version\>*.dll et Msvvcrt*\<version\>*.dll, avec la DLL.  
  
-   La création de la DLL est indépendante de la façon dont les classes sont implémentées.  La conception de DLL exporte uniquement pour les API que vous souhaitez.  Par conséquent, si l'implémentation change, les DLL standard sont encore valides.  
  
-   Avec les DLL standard qui lient statiquement à MFC, si la DLL et l'application utilisent MFC, il n'y a aucun problème avec les applications qui souhaitent une version différente de MFC que la DLL ou inversement.  Étant donné que la bibliothèque MFC est statiquement liée dans chaque DLL ou EXE, il n'y a aucun problème avec la version que vous avez.  
  
## limitations d'API  
 Certaines fonctionnalités de MFC ne s'appliquent pas à la version de DLL, soit en raison de les limitations techniques ou parce que ces services sont généralement fournis par l'application.  Avec la version actuelle de MFC, la seule fonction qui n'est pas applicable est `CWinApp::SetDialogBkColor`.  
  
## Générer la DLL  
 Lors de la compilation des DLL standard qui lient statiquement à MFC, les symboles `_USRDLL` et `_WINDLL` doivent être définis.  Le code de DLL doit également être compilé avec les commutateurs de compilation suivants :  
  
-   **\/D\_WINDLL** signifie que la compilation est pour une DLL  
  
-   **\/D\_USRDLL** spécifie que vous générez une DLL standard  
  
 Vous devez également définir ces symboles et utiliser les commutateurs de compilation lorsque vous compilez les DLL standard qui lient dynamiquement à MFC.  En outre, le symbole `_AFXDLL` doit être défini et le code de DLL doit être compilé avec :  
  
-   **\/D\_AFXDLL** spécifie que vous générez une DLL standard qui lie dynamiquement à MFC  
  
 Les interfaces \(API\) entre l'application et la DLL doivent être explicitement exportées.  Nous vous recommandons de définir des interfaces à faible bande passante, et utiliser ensuite uniquement des interfaces C si possible.  Il est plus facile à gérer les interfaces directes C que les classes plus complexes C\+\+.  
  
 Placez les API dans en\-tête distinct qui peut être inclus dans les fichiers C et C\+\+.  Consultez l'en\-tête ScreenCap.h dans l'exemple [DLLScreenCap](../top/visual-cpp-samples.md) de concepts avancés par MFC.  Pour exporter les fonctions, écrivez\-les dans la section `EXPORTS` de votre fichier de définition de module \(.DEF\) ou incluez `__declspec(dllexport)` dans les définitions de fonction.  Utilisez `__declspec(dllimport)` pour importer ces fonctions dans le fichier exécutable client.  
  
 Vous devez ajouter la macro `AFX_MANAGE_STATE` au début de toutes les fonctions exportées dans les DLL standard qui lient dynamiquement à MFC.  La macro définit l'état du module en cours à celui de la DLL.  Pour utiliser cette macro ajoutez la ligne de code suivante au début des fonctions exportées à partir de la DLL :  
  
 `AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`  
  
## WinMain \-\> DllMain  
 La bibliothèque MFC définit le point d'entrée standard Win32 `DllMain` qui initialise un objet dérivé par [CWinApp](../mfc/reference/cwinapp-class.md) comme dans une application classique de MFC.  Placez tout le code d'initialisation propre à la DLL dans la méthode [InitInstance](../Topic/CWinApp::InitInstance.md), comme dans une application MFC normale.  
  
 Remarquez que le mécanisme [CWinApp::Run](../Topic/CWinApp::Run.md) ne s'applique pas à une DLL, car c'est l'application qui possède la pompe de messages principale.  Si votre DLL affiche des boîtes de dialogue non modales ou possède une fenêtre de cadre principale qui lui est propre, la pompe de messages principale de votre application doit appeler une routine exportée par la DLL qui sollicite [CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md).  
  
 Pour obtenir un exemple de cette fonction, consultez  l'exemple DLLScreenCap.  
  
 La fonction `DllMain` que MFC fournit appelle la méthode [CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md) dérivée de votre classe `CWinApp`  avant que la DLL ne soit déchargée.  
  
## Lier la DLL  
 Avec les DLL standard qui lient statiquement à MFC, vous devez lier la DLL à Nafxcwd.lib ou Nafxcw.lib avec la version des runtimes C nommés Libcmt.lib.  Ces bibliothèques sont prégénérées et peuvent être installées en les spécifiant lorsque vous exécutez le programme d'installation de Visual C\+\+.  
  
## Exemple de code  
 Consultez l'exemple de programme DLLScreenCap de concepts avancés MFC pour obtenir un exemple complet.  Plusieurs choses intéressantes à noter dans cet exemple :  
  
-   Les flags de compilateur de la DLL et ceux de l'application sont différents.  
  
-   Les lignes de lien et les fichiers .DEF pour la DLL et ceux de l'application sont différents.  
  
-   Une application qui utilise la DLL ne doit pas être en C\+\+.  
  
-   L'interface entre l'application et la DLL est une API qui est utilisable par C ou C\+\+ et est exportée avec DLLScreenCap.def.  
  
 L'exemple suivant illustre une API définie dans une DLL standard qui lie statiquement à MFC.  Dans cet exemple, la déclaration est englobée dans un bloc `extern "C" { }` pour les utilisateurs C\+\+.  Cela a plusieurs avantages.  Tout d'abord, elle permet l'utilisation des API de votre DLL par des applications clientes non\-C\+\+.  Ensuite, elle réduit la charge mémoire de la DLL dans la mesure où la décoration C\+\+ n'est pas appliquée au nom exporté.  Enfin, elle facilite l'ajout explicite de fonctions à un fichier .def \(en vue d'une exportation ordinale\) en éliminant la contrainte de la décoration des noms.  
  
```  
#ifdef __cplusplus  
extern "C" {  
#endif  /* __cplusplus */  
  
struct TracerData  
{  
    BOOL    bEnabled;  
    UINT    flags;  
};  
  
BOOL PromptTraceFlags(TracerData FAR* lpData);  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 Les structures utilisées par l'API ne sont pas dérivées des classes de MFC et sont définies dans l'en\-tête d'API.  \+Il est ainsi possible de réduire la complexité de l'interface entre la DLL et l'application et rend la DLL utilisable pour les programmes C.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)