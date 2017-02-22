---
title: "Avertissement du compilateur (niveau 2) C4099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4099"
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 2) C4099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : nom de type déjà rencontré avec 'TypeObjet1' et utilisant maintenant 'TypeObjet2'  
  
 Un objet déclaré comme structure est défini comme classe ou un objet déclaré comme classe est défini comme structure.  Le compilateur utilise le type donné dans la définition.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4099 :  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```