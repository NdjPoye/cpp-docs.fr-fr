---
title: "Arri&#232;re-plan OLE&#160;: strat&#233;gies d&#39;impl&#233;mentation | Microsoft Docs"
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
  - "applications (OLE), implémenter OLE"
  - "OLE (C++), stratégie de développement"
  - "OLE (applications) (C++), implémenter OLE"
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Arri&#232;re-plan OLE&#160;: strat&#233;gies d&#39;impl&#233;mentation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Selon votre application, il existe quatre méthodes d'implémentation possibles pour ajouter la prise en charge OLE :  
  
-   Vous écrivez une nouvelle application.  
  
     Cette situation est généralement qui demande le moins le travail.  Lancez la Prise en charge des documents composés de l'Assistant Application MFC et sélectionnez soit les Propriétés Avancées ou le Support de Document Composé pour créer un squelette d'application.  Pour plus d'informations sur ces options et ce qu'elles font, consultez l'article [Créer un programme MFC EXE](../mfc/reference/mfc-application-wizard.md).  
  
-   Vous avez un programme écrit avec la version 2,0 de bibliothèque MFC ou une version ultérieure qui ne prend pas en charge OLE.  
  
     Créez une nouvelle application avec l'Assistant d'application MFC comme indiqué précédemment, puis copiez et collez le code de l'application dans votre application existante.  Cela fonctionne pour les serveurs, conteneurs, et les applications automatisées.  Consultez l'exemple [SCRIBBLE](../top/visual-cpp-samples.md) MFC pour obtenir un exemple de cette stratégie.  
  
-   Vous avez un programme de bibliothèque MFC qui implémente la prise en charge de la version 1.0 d'OLE.  
  
     Consultez [Note technique 41 en MFC](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md) pour cette stratégie de conversion.  
  
-   Vous possédez une application qui n'a pas été écrite à l'aide de Microsoft Foundation Classes et qui peut avoir ou non implémenté la prise en charge OLE.  
  
     Cette situation est celle qui implique le plus de travail.  Une approche consiste à créer une nouvelle application, comme dans la première stratégie, puis à copier et coller le code existant dans celle\-ci.  Si votre code existant est écrit en C, vous devrez peut\-être le changer afin qu'il puisse être compilé en tant que code C\+\+.  Si votre code C appelle l'API Windows, vous ne devez pas le modifier pour utiliser les classes Microsoft Foundation.  Cette approche demandera probablement d'une certaine restructuration de votre programme pour prendre en charge l'architecture document\/Vue utilisée par les versions 2,0 et supérieures des classes Microsoft Foundation.  Pour plus d'informations sur cette architecture, consultez la [Note technique 25](../mfc/tn025-document-view-and-frame-creation.md).  
  
 Une fois que vous avez décidé d'une stratégie, vous devez lire les articles [Conteneurs](../mfc/containers.md) ou [Serveurs](../mfc/servers.md) \(selon le type d'application que vous écrivez\) ou examiner les exemples de programmation, ou les deux.  Les exemples de MFC OLE [OCLIENT](../top/visual-cpp-samples.md) et [HIERSVR](../top/visual-cpp-samples.md) indiquent comment implémenter les différents aspects des conteneurs et des serveurs, respectivement.  À différents points au cours de ces articles, vous vous verrez référé à certaines fonctions dans ces extraits en tant qu'exemples de la technique présentée à ce moment.  
  
## Voir aussi  
 [Arrière\-plan OLE](../mfc/ole-background.md)   
 [Conteneurs : implémentation d'un conteneur](../mfc/containers-implementing-a-container.md)   
 [Serveurs : implémentation d'un serveur](../mfc/servers-implementing-a-server.md)   
 [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md)