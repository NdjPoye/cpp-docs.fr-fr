---
title: "Erreur du compilateur C2286 | Microsoft Docs"
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
  - "C2286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2286"
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la représentation des pointeurs vers des membres 'identificateur' est déjà définie à 'héritage' \- déclaration ignorée  
  
 Il existe deux représentations différentes des pointeurs vers membres pour la classe.  
  
 Pour plus d'informations, consultez [Mots clé d'héritage](../../cpp/inheritance-keywords.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2286 :  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```