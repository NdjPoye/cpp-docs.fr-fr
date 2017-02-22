---
title: "Avertissement du compilateur (niveau 4) C4611 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4611"
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 4) C4611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'interaction entre 'fonction' et la destruction d'objet C\+\+ n'est pas portable  
  
 Sur certaines plateformes, les fonctions qui contiennent **catch** peuvent ne pas prendre en charge la sémantique de destruction d'objet C\+\+ lorsqu'elle est hors de portée.  
  
 Pour éviter un comportement inattendu, évitez d'utiliser **catch** dans les fonctions qui possèdent des constructeurs et des destructeurs.  
  
 Cet avertissement n'apparaît qu'une seule fois ; consultez [pragma warning](../../preprocessor/warning.md).