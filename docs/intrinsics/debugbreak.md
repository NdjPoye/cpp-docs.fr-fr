---
title: "__debugbreak | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__debugbreak_cpp"
  - "__debugbreak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__debugbreak (intrinsèque)"
  - "points d'arrêt, __debugbreak (intrinsèque)"
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __debugbreak
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Génère un point d'arrêt dans votre code, où l'utilisateur sera invité à exécuter le débogueur.  
  
## Syntaxe  
  
```  
void __debugbreak();  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
  
## Notes  
 L'intrinsèque `__debugbreak` du compilateur, similaire à [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), est une manière Win32 portable de générer un point d'arrêt.  
  
> [!NOTE]
>  Lors de la compilation avec **\/clr**, une fonction contenant `__debugbreak` sera compilée en langage MSIL.  `asm int 3` entraîne la compilation d'une fonction en code natif.  Pour plus d'informations, consultez [\_\_asm](../assembler/inline/asm.md).  
  
 Par exemple :  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 est similaire à :  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 sur un ordinateur x86.  
  
 Cette routine est disponible uniquement en tant qu'intrinsèque.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)