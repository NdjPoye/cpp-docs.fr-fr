---
title: "DLL normales li&#233;es de mani&#232;re dynamique aux MFC | Microsoft Docs"
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
  - "AFX_MANAGE_STATE (macro)"
  - "DLL (C++), normales"
  - "DLL liées dynamiquement (C++)"
  - "DLL normales (C++), liées dynamiquement à MFC"
  - "versions DLL partagées (C++)"
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL normales li&#233;es de mani&#232;re dynamique aux MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une DLL normale liée de manière dynamique aux MFC est une DLL qui utilise les MFC en interne, et les fonctions exportées de la DLL peuvent être appelées par des exécutables MFC ou non\-MFC.  Comme son nom l'indique, ce type de DLL est généré à l'aide de la version bibliothèque de liens dynamiques des MFC \(appelée également version partagée des MFC\).  Les fonctions sont généralement exportées à partir d'une DLL normale à l'aide de l'interface C standard.  
  
 Vous devez ajouter la macro `AFX_MANAGE_STATE` au début de toutes les fonctions exportées des DLL normales qui sont liées de manière dynamique aux MFC pour définir l'état du module en cours comme étant celui de la DLL.  Pour cela, ajoutez la ligne de code suivante au début des fonctions exportées à partir de la DLL :  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Une DLL normale liée de manière dynamique aux MFC présente les fonctionnalités suivantes :  
  
-   Il s'agit d'un nouveau type de DLL introduit par Visual C\+\+ 4.0.  
  
-   L'exécutable client peut être écrit dans n'importe quel langage prenant en charge l'emploi des DLL \(C, C\+\+, Pascal, Visual Basic, etc.\) ; il ne doit pas s'agir nécessairement d'une application MFC.  
  
-   Contrairement aux DLL normales liées de manière statique, ce type de DLL est lié de manière dynamique aux DLL MFC \(appelées également DLL MFC partagées\).  
  
-   La bibliothèque d'importation MFC liée à ce type de DLL est la même que celle employée pour les DLL d'extension ou les applications utilisant la DLL MFC : MFCxx\(D\).lib.  
  
 Une DLL normale liée de manière dynamique aux MFC doit répondre aux critères suivants :  
  
-   Ce type de DLL est compilé avec le symbole **\_AFXDLL** défini, tout comme un exécutable lié de manière dynamique à la DLL MFC.  Cependant, le symbole **\_USRDLL** est aussi défini, tout comme une DLL normale liée de manière statique aux MFC.  
  
-   Ce type de DLL doit instancier une classe dérivée de `CWinApp`.  
  
-   Ce type de DLL utilise la fonction `DllMain` fournie par les MFC.  Placez tout le code d'initialisation des DLL dans une fonction membre `InitInstance` et le code d'arrêt dans `ExitInstance`, comme dans une application MFC normale.  
  
 Dans la mesure où ce type de DLL utilise la version bibliothèque de liens dynamiques des MFC, vous devez définir explicitement l'état du module en cours comme étant celui de la DLL.  Pour ce faire, utilisez la macro [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) au début de chaque fonction exportée à partir de la DLL.  
  
 À l'instar des applications MFC, les DLL normales doivent posséder une classe dérivée de `CWinApp` et un objet unique de cette classe d'application.  Cependant, et contrairement à l'objet `CWinApp` d'une application, l'objet `CWinApp` de la DLL ne possède pas une pompe de messages principale.  
  
 Remarquez que le mécanisme `CWinApp::Run` ne s'applique pas à une DLL, car c'est l'application qui possède la pompe de messages principale.  Si votre DLL met en œuvre des boîtes de dialogue non modales ou possède une fenêtre frame principale propre, la pompe de messages principale de votre application doit appeler une routine exportée par la DLL qui sollicite `CWinApp::PreTranslateMessage`.  
  
 Placez tout le code d'initialisation propre à la DLL dans la fonction membre `CWinApp::InitInstance`, comme dans une application MFC normale.  La fonction membre `CWinApp::ExitInstance` de votre classe dérivée `CWinApp` est appelée à partir de la fonction `DllMain` mise en œuvre par les MFC avant le déchargement de la DLL.  
  
 Vous devez distribuer les DLL partagées MFCx0.dll et Msvcr\*0.dll \(ou des fichiers similaires\) avec votre application.  
  
 Une DLL liée de manière dynamique aux MFC ne peut pas non plus être liée de manière statique aux MFC.  Les applications peuvent s'attacher aux DLL normales liées de manière dynamique aux MFC comme à n'importe quelle autre DLL.  
  
 Les symboles sont généralement exportés à partir d'une DLL normale à l'aide de l'interface C standard.  La déclaration d'une fonction exportée à partir d'une DLL normale ressemble à ceci :  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Toutes les allocations de mémoire effectuées dans une DLL normale doivent rester au sein de celle\-ci ; la DLL ne doit ni passer à l'exécutable appelant ni recevoir de lui l'un des éléments suivants :  
  
-   Pointeurs désignant des objets MFC  
  
-   Pointeurs désignant une mémoire allouée par les MFC  
  
 Si vous devez réaliser l'une des tâches ci\-dessus ou si vous devez passer des objets dérivés des MFC entre l'exécutable appelant et la DLL, il vous faut alors générer une DLL d'extension.  
  
 La passation de pointeurs désignant la mémoire, qui ont été alloués par les bibliothèques runtime du C, entre une application et une DLL est sécurisée seulement si vous effectuez une copie des données.  Vous ne devez ni supprimer ni redimensionner ces pointeurs et encore moins les utiliser avant d'avoir fait une copie de la mémoire.  
  
 Lors de la génération d'une DLL normale liée de manière dynamique aux MFC, vous devez utiliser la macro [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) pour changer correctement l'état du module MFC.  Pour cela, ajoutez la ligne de code suivante au début des fonctions exportées à partir de la DLL :  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 La macro **AFX\_MANAGE\_STATE** ne doit pas être utilisée dans les DLL normales liées de manière statique aux MFC et dans les DLL d'extension.  Pour plus d'informations, consultez [Gestion des données d'état des modules MFC](../mfc/managing-the-state-data-of-mfc-modules.md).  
  
 Pour obtenir un exemple de la procédure à suivre pour écrire, générer et utiliser une DLL normale, consultez [DLLScreenCap](http://msdn.microsoft.com/fr-fr/2171291d-3a50-403b-90a1-d93c2acb4f4a).  Pour plus d'informations sur les DLL normales liées de manière dynamique aux MFC, consultez la section intitulée « Conversion de DLLScreenCap pour une liaison dynamique à la DLL MFC » dans l'extrait de l'exemple.  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser des DLL normales](../build/initializing-regular-dlls.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [États du module d'une DLL normale liée de manière dynamique aux MFC](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
  
-   [Gestion des données d'état des modules MFC](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Utilisation de DLL d'extension de type base de données, OLE et sockets dans des DLL normales](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [Utilisation de MFC dans le cadre d'une DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
## Voir aussi  
 [Types de DLL](../build/kinds-of-dlls.md)