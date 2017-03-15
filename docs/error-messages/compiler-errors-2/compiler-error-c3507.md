---
title: "Erreur du compilateur C3507 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3507"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3507"
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3507
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un ProgID ne peut pas être un 'id' de plus de 39 caractères, ni contenir de signe de ponctuation autre que '.', ni commencer par un chiffre  
  
 L'attribut [progid](../../windows/progid.md) présente des restrictions pour les valeurs qu'il peut prendre.  
  
 L'exemple suivant génère l'erreur C3507 :  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```