---
title: "MASM for x64 (ml64.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ml64.exe"
  - "ml"
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MASM for x64 (ml64.exe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ml64.exe est un assembly qui accepte le langage assembleur de [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] .  Pour plus d'informations sur les options du compilateur de ml64.exe, consultez [ML and ML64 Command\-Line Reference](../../assembler/masm/ml-and-ml64-command-line-reference.md).  
  
 L'ASM intégré \(IDE\) n'est pas pris en charge pour [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].  utilisation MASM ou intrinsèques du compilateur \([x64 Intrinsics](http://msdn.microsoft.com/fr-fr/5d1f5d3e-156e-4ebf-932e-fd09be7ced62)\).  
  
 Les deux solutions de contournement sont un assembly séparé avec MASM \(qui prend complètement en charge x64\) et intrinsèques du compilateur.  Nous avons ajouté de nombreux intrinsèques pour permettre aux clients pour utiliser l'instruction offrent spéciale\-fonction \(par exemple.  analyse privilégiée, de bits\/test, verrouillées, etc.…\) dans aussi près à la multiplateforme façon que possible.  
  
## directives de ml64\-Specific  
 utilisez les directives suivantes avec ml64.exe :  
  
-   [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)  
  
-   [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../../assembler/masm/dot-pushreg.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
 En outre, la directive de [PROC](../../assembler/masm/proc.md) a été mise à jour pour une utilisation avec ml64.exe.  
  
## mode d'adresse 32 bits \(substitution de taille d'adresse\)  
 MASM émettra la substitution de taille de l'adresse 0x67 si un opérande de mémoire inclut les registres 32 bits.  par exemple, les exemples suivants provoquent la substitution de taille d'adresse à émettre :  
  
```  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
 MASM suppose que si un décalage 32 bits seul apparaît comme opérande de mémoire, le adressage 64 bits est attendu.  Il n'existe actuellement pas de prise en charge l'adressage 32 bits avec ces opérandes.  
  
 Enfin, combiner les tailles de registre dans un opérande de mémoire, comme indiqué dans le code suivant, génère une erreur.  
  
```  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## Voir aussi  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)