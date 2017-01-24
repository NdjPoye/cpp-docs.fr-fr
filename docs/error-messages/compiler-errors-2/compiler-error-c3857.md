---
title: "Erreur du compilateur C3857 | Microsoft Docs"
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
  - "C3857"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3857"
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3857
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : plusieurs listes de paramètres de type ne sont pas autorisées  
  
 Plusieurs modèles ou génériques ont été spécifiés pour le même type, ce qui n'est pas autorisé.  
  
 L'exemple suivant génère l'erreur C3857 :  
  
```  
// C3857.cpp  
template <class T, class TT>  
template <class T2>    // C3857  
struct B {};  
```  
  
 Résolution possible :  
  
```  
// C3857b.cpp  
// compile with: /c  
template <class T, class TT, class T2>   
struct B {};  
```  
  
 L'erreur C3857 peut également se produire lors de l'utilisation de génériques :  
  
```  
// C3857c.cpp  
// compile with: /clr  
generic <typename T>  
generic <typename U>  
ref class GC;   // C3857  
```  
  
 Résolution possible :  
  
```  
// C3857d.cpp  
// compile with: /clr /c  
generic <typename U>  
ref class GC;  
```