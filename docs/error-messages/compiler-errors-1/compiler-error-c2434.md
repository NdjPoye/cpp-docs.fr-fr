---
title: "Erreur du compilateur C2434 | Microsoft Docs"
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
  - "C2434"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2434"
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2434
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole' : un symbole déclaré avec \_\_declspec\(process\) ne peut pas être initialisé dynamiquement en mode \/clr:pure  
  
 Il n'est pas possible d'initialiser dynamiquement une variable par processus en mode **\/clr:pure**.  Pour plus d’informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) et [processus](../../cpp/process.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2434 :  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```