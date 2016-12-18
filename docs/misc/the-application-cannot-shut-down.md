---
title: "The application cannot shut down. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A0029"
  - "vs.message.VB_E_IDWCANTEXITDLG"
ms.assetid: 7c720238-c17e-4a75-bd34-d2fdcbb38a01
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The application cannot shut down.
Ce message d'erreur apparaît généralement lorsqu'un programme extérieur \(par exemple, le Gestionnaire des tâches\) essaie de fermer Visual Studio alors que celui\-ci contient encore une boîte de dialogue modale ouverte.  
  
### Pour corriger cette erreur  
  
1.  Fermez la boîte de dialogue modale et recommencez.