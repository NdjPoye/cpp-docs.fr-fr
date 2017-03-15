---
title: "DLL normales li&#233;es de mani&#232;re statique aux MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), normales"
  - "DLL normales (C++)"
  - "DLL normales (C++), liées de manière statique aux MFC"
  - "DLL liées de manière statique (C++)"
  - "USRDLL"
  - "USRDLL, liées de manière statique aux MFC"
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# DLL normales li&#233;es de mani&#232;re statique aux MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une DLL normale liée de manière statique aux MFC est une DLL qui utilise les MFC en interne, et les fonctions exportées de la DLL peuvent être appelées par des exécutables MFC ou non\-MFC.  Comme l'indique son nom, ce type de DLL est généré à l'aide de la version bibliothèque de liaison statique des MFC.  Les fonctions sont généralement exportées à partir d'une DLL normale à l'aide de l'interface C standard.  Pour obtenir un exemple de la procédure à suivre pour écrire, générer et utiliser une DLL normale, consultez [DLLScreenCap](http://msdn.microsoft.com/fr-fr/2171291d-3a50-403b-90a1-d93c2acb4f4a).  
  
 Remarquez que le terme USRDLL n'a plus cours dans la documentation Visual C\+\+.  Une DLL normale liée de manière statique aux MFC possède les mêmes caractéristiques que l'ancienne USRDLL.  
  
 Une DLL normale liée de manière statique aux MFC se caractérise par les fonctionnalités suivantes :  
  
-   L'exécutable client peut être écrit dans n'importe quel langage prenant en charge l'emploi des DLL \(C, C\+\+, Pascal, Visual Basic, etc.\) ; il ne doit pas s'agir nécessairement d'une application MFC.  
  
-   La DLL peut être liée aux mêmes bibliothèques de liaisons statiques MFC que celles utilisées par les applications.  Il n'existe plus de version séparée des bibliothèques de liaisons statiques pour les DLL.  
  
-   Avant la version 4.0 des MFC, les USRDLL offraient le même type de fonctionnalités que les DLL normales liées de manière statique aux MFC.  Le terme USRDLL est obsolète depuis la version 4.0 de Visual C\+\+.  
  
 Une DLL normale liée de manière statique aux MFC doit répondre aux critères suivants :  
  
-   Ce type de DLL doit instancier une classe dérivée de `CWinApp`.  
  
-   Ce type de DLL utilise la fonction `DllMain` fournie par les MFC.  Placez tout le code d'initialisation des DLL dans une fonction membre `InitInstance` et le code d'arrêt dans `ExitInstance`, comme dans une application MFC normale.  
  
-   Même si le terme USRDLL est obsolète, vous devez toujours définir "**\_USRDLL**" sur la ligne de commande du compilateur.  Cette définition détermine les déclarations qui sont extraites à partir des fichiers d'en\-tête MFC.  
  
 À l'instar des applications MFC, les DLL normales doivent posséder une classe dérivée de `CWinApp` et un objet unique de cette classe d'application.  Cependant, et contrairement à l'objet `CWinApp` d'une application, l'objet `CWinApp` de la DLL ne possède pas une pompe de messages principale.  
  
 Remarquez que le mécanisme `CWinApp::Run` ne s'applique pas à une DLL, car c'est l'application qui possède la pompe de messages principale.  Si la DLL ouvre des boîtes de dialogue non modales ou possède une fenêtre frame principale propre, la pompe de messages principale de l'application doit appeler une routine exportée par la DLL qui appelle à son tour la fonction membre `CWinApp::PreTranslateMessage` de l'objet application de la DLL.  
  
 Pour obtenir un exemple de cette fonction, consultez  l'exemple DLLScreenCap.  
  
 Les symboles sont généralement exportés à partir d'une DLL normale à l'aide de l'interface C standard.  La déclaration d'une fonction exportée à partir d'une DLL normale ressemble à ceci :  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 Toutes les allocations de mémoire effectuées dans une DLL normale doivent rester au sein de celle\-ci ; la DLL ne doit ni passer à l'exécutable appelant ni recevoir de lui l'un des éléments suivants :  
  
-   Pointeurs désignant des objets MFC  
  
-   Pointeurs désignant une mémoire allouée par les MFC  
  
 Si vous devez réaliser l'une des tâches ci\-dessus ou passer des objets dérivés des MFC entre l'exécutable appelant et la DLL, il vous faut alors générer une DLL d'extension.  
  
 La passation de pointeurs désignant la mémoire, qui ont été alloués par les bibliothèques runtime du C, entre une application et une DLL est sécurisée seulement si vous effectuez une copie des données.  Vous ne devez ni supprimer ni redimensionner ces pointeurs et encore moins les utiliser avant d'avoir fait une copie de la mémoire.  
  
 Une DLL liée de manière statique aux MFC ne peut pas non plus être liée de manière dynamique aux DLL MFC partagées.  Une DLL liée de manière statique aux MFC peut être rattachée dynamiquement à une application comme n'importe quelle autre DLL ; les applications lui sont liées comme à n'importe quelle autre DLL.  
  
 Les bibliothèques de liaisons statiques MFC standard sont nommées selon la convention décrite dans la rubrique [Conventions d'attribution de noms aux DLL MFC](../build/naming-conventions-for-mfc-dlls.md).  Toutefois, dans la version 3.0 de MFC et versions ultérieures, il n'est plus nécessaire de spécifier manuellement à l'éditeur de liens la version de la bibliothèque MFC dans laquelle vous souhaitez lier.  À la place, les fichiers d'en\-tête MFC déterminent automatiquement la version correcte de la bibliothèque MFC dans laquelle lier en fonction des définitions du préprocesseur, telles que **\_DEBUG** ou **\_UNICODE**.  Les fichiers d'en\-tête MFC ajoutent les directives \/DEFAULTLIB en demandant à l'éditeur de liens d'établir la liaison avec une version spécifique de la bibliothèque MFC.  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser des DLL normales](../build/initializing-regular-dlls.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation de MFC dans le cadre d'une DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [Utilisation de DLL d'extension de type base de données, OLE et sockets dans des DLL normales](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [Création d'une DLL MFC](../mfc/reference/mfc-dll-wizard.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL d'extension](../build/extension-dlls-overview.md)  
  
## Voir aussi  
 [Types de DLL](../build/kinds-of-dlls.md)