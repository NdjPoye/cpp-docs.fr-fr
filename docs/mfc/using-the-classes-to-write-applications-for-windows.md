---
title: "Utilisation des classes pour l&#39;&#233;criture d&#39;applications pour Windows | Microsoft Docs"
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
  - "applications (OLE), infrastructure de l'application MFC"
  - "applications de base de données (C++), créer"
  - "MFC (C++), développement de l'application"
  - "contrôles ActiveX MFC, créer"
  - "OLE (applications) (C++), infrastructure de l'application MFC"
  - "applications Windows (C++), infrastructure de l'application MFC"
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des classes pour l&#39;&#233;criture d&#39;applications pour Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prises ensemble, les classes dans la bibliothèque Microsoft Foundation Class \(MFC\) « constituent un framework d'application, » sur lequelle vous créez une application pour le système d'exploitation Windows.  À un niveau très général, le framework définit la structure d'une application et fournit les implémentations standard d'une interface utilisateur qui peuvent être placées sur la structure.  Votre travail en tant que programmeur consiste à terminer le reste de la structure, qui sont les éléments qui sont spécifiques à votre application.  Vous pouvez obtenir un avantage en utilisant l'Assistant d'application MFC pour créer des fichiers pour un d'abut d'application très complet.  Utilisez les éditeurs de ressources Microsoft Visual C\+\+ pour concevoir vos éléments d'interface utilisateur visuellement, les commandes d'Affichage de classes pour connecter ces éléments à coder, et la bibliothèque de classes pour implémenter la logique spécifique à l'application.  
  
 La version 3.0 ou ultérieure du framework MFC gère la programmation pour les plateformes Win32, notamment Microsoft Windows 95 et les versions ultérieures, la version 3.51 de Windows NT et les versions ultérieures.  MFC Win32 inclut le multithreading.  Utilisez la version 1.5*x* si vous devez effectuer programmation 16 bits.  
  
 La famille des articles présente une vision d'ensemble large du framework d'application.  Elle explore également les objets principaux qui composent votre application et comment ils sont créés.  Parmi les rubriques traitées dans ces éléments, il y a les suivantes :  
  
-   [Le framework](../mfc/framework-mfc.md).  
  
-   Répartition des tâches entre le framework et votre code, comme décrit dans [Génération de l'infrastructure](../mfc/building-on-the-framework.md).  
  
-   [La classe d'application](../mfc/cwinapp-the-application-class.md), qui encapsule les fonctionnalités au niveau de l'application.  
  
-   Comment les [modèles de document](../mfc/document-templates-and-the-document-view-creation-process.md) vréent et gèrent des documents et les vues associées et les fenêtres cadres.  
  
-   Classe [CWnd](../mfc/window-objects.md), la classe de base racine de toutes les fenêtres.  
  
-   [Objets graphiques](../mfc/graphic-objects.md), tels que les stylets et les pinceaux.  
  
 D'autres composants du framework incluent :  
  
-   [Window objets : Vue d'ensemble](../mfc/window-objects.md)  
  
-   [Gestion et mappage des messages](../mfc/message-handling-and-mapping.md)  
  
-   [CObject, la classe de base racine de MFC](../mfc/using-cobject.md)  
  
-   [Architecture document\/vue](../mfc/document-view-architecture.md)  
  
-   [Boîtes de dialogue](../mfc/dialog-boxes.md)  
  
-   [des contrôles.](../mfc/controls-mfc.md)  
  
-   [Barres de contrôles](../mfc/control-bars.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [Gestion de la mémoire](../mfc/memory-management.md)  
  
     En plus de vous donner un avantage dans l'écriture d'applications pour le système d'exploitation Windows, MFC simplifie également l'écriture d'applications qui utilisent la technologie de liaison et d'incorporation OLE.  Vous pouvez faire de votre application un conteneur de modification visuel OLE, un serveur de modification visuel OLE, ou les deux, et vous pouvez ajouter l'automatisation de sorte que d'autres applications peuvent utiliser des objets de votre application ou le même lecteur à distance.  
  
-   [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)  
  
     Le kit de développement \(CDK\) de contrôle OLE est maintenant entièrement intégré au framework.  La famille d'article fournit une vue d'ensemble du développement de contrôle ActiveX avec MFC. \(Les contrôles ActiveX étaient auparavant appelés les contrôles OLE.\)  
  
-   [Programmation de base de données](../data/data-access-programming-mfc-atl.md)  
  
     MFC fournit également deux jeux de classes de base de données qui simplifient l'écriture d'applications d'accès aux données.  En utilisant des classes de base de données ODBC, vous pouvez vous connecter aux bases de données via un pilote ODBC \(Open Database Connectivity\), sélectionner des enregistrements depuis les tables, et afficher des informations d'enregistrement dans un formulaire affiché à l'écran.  À l'aide des classes d'accès aux données \(DAO\), vous pouvez travailler avec les bases de données via le moteur de base de données Microsoft Jet ou des sources de données externes \(non Jet\), notamment les sources de données ODBC.  
  
     En outre, MFC est entièrement conçu pour écrire des applications qui utilisent Unicode et les jeux de caractères multioctets \(MBCS\), notamment les jeux de caractères codés sur deux octets \(DBCS\).  
  
 Pour obtenir un guide général de la documentation de MFC, consultez [Rubriques de général MFC](../mfc/general-mfc-topics.md).  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)