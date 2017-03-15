---
title: "Erreur du compilateur C2592 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2592"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2592"
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2592
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : 'base\_class\_2' est hérité de 'base\_class\_1' et ne peut pas être spécifié de nouveau  
  
 Vous ne pouvez spécifier que les classes de base qui n'héritent pas d'autres classes de base.  Dans ce cas, seul `base_class_1` est nécessaire dans la spécification de `class` car `base_class_1` hérite déjà de `base_class_2`.