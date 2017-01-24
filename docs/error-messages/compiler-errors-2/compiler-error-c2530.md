---
title: "Erreur du compilateur C2530 | Microsoft Docs"
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
  - "C2530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2530"
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : les références doivent être initialisées  
  
 Vous devez initialiser une référence lorsque vous la déclarez, sauf si elle est déjà déclarée :  
  
-   avec le mot clé [extern](../../cpp/using-extern-to-specify-linkage.md) ;  
  
-   en tant que membre d'une classe, d'une structure ou d'une union \(et elle est initialisée dans le constructeur\) ;  
  
-   en tant que paramètre d'une déclaration ou d'une définition de fonctions ;  
  
-   en tant que type de retour d'une fonction.  
  
 L'exemple suivant génère l'erreur C2530 :  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```