---
title: "Erreur du compilateur C2435 | Microsoft Docs"
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
  - "C2435"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2435"
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2435
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : l'initialisation dynamique requiert un CRT managé, impossible de compiler avec \/clr:safe  
  
 L'initialisation de variable globale de domaine par application exige la compilation du CRT avec `/clr:pure`, ce qui ne produit pas d'image vérifiable.  
  
 Pour plus d'informations, consultez [appdomain](../../cpp/appdomain.md) et [process](../../cpp/process.md).  
  
 L'exemple suivant génère l'erreur C2435 :  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```