---
title: ".MODEL | Microsoft Docs"
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
  - ".MODEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".MODEL directive"
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .MODEL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialise le modèle de mémoire du programme.  
  
## Syntaxe  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### Paramètres  
 `memorymodel`  
 Paramètre requis qui détermine la taille des pointeurs de données et le code.  
  
 `langtype`  
 Paramètre facultatif qui définit les conventions d'appel et d'appellation des procédures et des symboles publics.  
  
 `stackoption`  
 Paramètre facultatif.  
  
 `stackoption`is not used if `memorymodel` is `FLAT`.  
  
 Spécification de `NEARSTACK` regroupe le segment de pile dans un seul segment physique \(`DGROUP`\) ainsi que des données.  Le Registre de segment de pile \(`SS`\) est supposé pour contenir la même adresse que le Registre de segment de données \(`DS`\).  `FARSTACK`ne pas grouper la pile avec `DGROUP`; Ainsi, `SS` n'est pas égale `DS`.  
  
## Notes  
 .`MODEL`n'est pas utilisé dans [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 Le tableau suivant répertorie les valeurs possibles pour chaque paramètre lorsque vous ciblez les plates\-formes 16 bits et 32 bits :  
  
|Paramètre|valeurs de 32 bits|valeurs 16 bits \(prise en charge pour le développement de 16 bits antérieur\)|  
|---------------|------------------------|------------------------------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|Non utilisé|`NEARSTACK`, `FARSTACK`|  
  
## Code  
 Exemples MASM liés, de télécharger les exemples du compilateur à partir de [exemples Visual C\+\+ et la Documentation associée pour 2010 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=178749).  
  
 L'exemple suivant illustre l'utilisation de la `.MODEL` la directive.  
  
## Exemple  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [Exemples Visual C\+\+ et la Documentation associée pour 2010 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=178749)