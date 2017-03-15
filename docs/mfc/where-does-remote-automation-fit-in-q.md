---
title: "Quand l&#39;automation &#224; distance convient-elle&#160;? | Microsoft Docs"
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
  - "Automation à distance, DCOM"
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Quand l&#39;automation &#224; distance convient-elle&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM a été publié en 1996 et est disponible avec les plateformes 32 bits et 64 bits uniquement.  L'équipe Visual Basic de Microsoft a toujours vu Visual Basic comme utiliser Automation pour permettre à ses composants de communiquer.  Le manque d'une version distribuée a sérieusement limité l'utilisation de ces fonctions dans les environnements d'entreprise,donc l'équipe de développement Visual Basic 4.0 Enterprise Edition a décidé d'étudier la création de son propre ensemble de composants de communication à distance pour les parties Automation de OLE et COM.  Sans ambiguïté, un objectif important était de garantir que le résultat serait compatible avec et pourrait être remplacé par DCOM lorsqu'il serait devenu disponible.  Ils ont ensuite implémenté Remote Automation \(RA\) pour les plateformes Windows 16 bits et 32 bits.  
  
 L'automatisation distante n'est liée à un langage spécifique, mais jusqu'à la version de Visual C\+\+ 4.2 Enterprise Edition, elle a été expédiée uniquement avec Visual Basic 4.0.  Notez que Remote Automation est entièrement liée par DCOM.  Si vous avez la possibilité d'utiliser DCOM au lieu de Remote Automation dans vos applications, vous devriez le faire.  Toutefois, il existe des scénarios où Remote Automation est plus approprié :  
  
-   Quand vous avez des clients 16 bits.  
  
-   Si votre organisation n'a pas encore déroulé une version compatible DCOM de Windows NT ou Windows 95.  
  
-   Si vous mettez à niveau une suite d'applications existantes qui utilise l'automatisation à distance pour utiliser des composants C\+\+ à la place d'un ou plusieurs composants de Visual Basic.  
  
 Il ne faut pas de différences entre les programmes créés pour utiliser Remote Automation et ceux créés pour utiliser Automation via DCOM, et les utilitaires de configuration rendent très simple le basculement entre Remote Automation et DCOM.  Par conséquent, il n'est pas difficile à mettre à niveau une application de Remote Automation à DCOM une fois l'infrastructure en place.  
  
## Voir aussi  
 [Que fournit l'automation à distance ?](../mfc/what-does-remote-automation-provide-q.md)   
 [Historique de DCOM](../mfc/history-of-dcom.md)