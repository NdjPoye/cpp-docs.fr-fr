---
title: "Erreur du compilateur C2834 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2834"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2834"
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2834
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator opérateur' doit être globalement qualifié  
  
 Les opérateurs `new` et `delete` sont liés à la classe dans laquelle ils résident.  La résolution de la portée ne peut pas être utilisée pour sélectionner une version de `new` ou `delete` d'une classe différente.  Pour implémenter plusieurs formes de l'opérateur `new` ou `delete`, créez une version de l'opérateur avec des paramètres formels supplémentaires.