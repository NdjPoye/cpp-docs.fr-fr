---
title: "Avertissement du compilateur (niveau 1) C4079 | Microsoft Docs"
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
  - "C4079"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4079"
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4079
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jeton 'jeton' inattendu  
  
 Un jeton séparateur inattendu apparaît dans une liste d'arguments de pragma.  Le reste du pragma a été ignoré.  
  
 L'exemple suivant génère l'erreur C4079 :  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```