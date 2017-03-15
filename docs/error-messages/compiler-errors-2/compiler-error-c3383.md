---
title: "Erreur du compilateur C3383 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3383"
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator new' n'est pas pris en charge avec \/clr:safe  
  
 Le fichier de sortie d’une compilation **\/clr:safe** est un fichier de type sécurisé vérifiable qui ne prend pas en charge les pointeurs.  
  
 Pour plus d'informations, consultez  
  
-   [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Problèmes courants de migration vers Visual C\+\+ 64 bits](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Exemple  
 L’exemple suivant génère l’erreur C3383.  
  
```  
// C3383.cpp // compile with: /clr:safe int main() { char* pCharArray = new char[256];  // C3383 }  
```