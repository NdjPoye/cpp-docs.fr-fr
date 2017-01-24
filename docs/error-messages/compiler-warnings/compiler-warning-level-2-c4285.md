---
title: "Avertissement du compilateur (niveau 2) C4285 | Microsoft Docs"
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
  - "C4285"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4285"
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4285
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le type de retour de 'identificateur::opérateur –\>' est récurrent si appliqué à l'aide de la notation infix  
  
 La fonction **opérateur–\>\(\)** spécifiée ne peut pas retourner le type pour lequel elle est définie ou une référence au type pour lequel elle est définie.  
  
 L'exemple suivant génère l'erreur C4285 :  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```