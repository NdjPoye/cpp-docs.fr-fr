---
title: "Erreur du compilateur C3862 | Microsoft Docs"
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
  - "C3862"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3862"
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3862
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : impossible de compiler une fonction non managée avec \/clr:pure ou \/clr:safe  
  
 Une compilation avec **\/clr:pure** ou **\/clr:safe** produit une image MSIL uniquement, c'est\-à\-dire une image sans code natif \(non managé\).  Par conséquent, vous ne pouvez pas utiliser le pragma `unmanaged` dans une compilation **\/clr:pure** ou **\/clr:safe** .  
  
 Pour plus d’informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) et [managé, non managé](../../preprocessor/managed-unmanaged.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3862 :  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```