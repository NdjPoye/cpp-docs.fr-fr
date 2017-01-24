---
title: "Erreur du compilateur C2505 | Microsoft Docs"
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
  - "C2505"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2505"
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2505
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : '\_\_declspec\(modifier\)' ne peut s'appliquer qu'aux déclarations ou définitions d'objets globaux ou de données membres static  
  
 Un modificateur `__declspec` destiné uniquement à être utilisé au niveau de la portée globale a été utilisé dans une fonction.  
  
 Pour plus d'informations, consultez [appdomain](../../cpp/appdomain.md) et [process](../../cpp/process.md).  
  
 L'exemple suivant génère l'erreur C2505 :  
  
```  
// C2505.cpp  
// compile with: /clr  
  
// OK  
__declspec(process) int ii;  
__declspec(appdomain) int jj;  
  
int main() {  
   __declspec(process) int i;   // C2505  
   __declspec(appdomain) int j;   // C2505  
}  
```