---
title: "Avertissement du compilateur (niveaux&#160;1 et 3) C4793 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4793"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4793"
  - "C6630"
  - "C6631"
  - "C6634"
  - "C6635"
  - "C6636"
  - "C6637"
  - "C6638"
  - "C6639"
  - "C6640"
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# Avertissement du compilateur (niveaux&#160;1 et 3) C4793
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la fonction est compilée comme code natif : 'raison'  
  
 Le compilateur ne peut pas compiler la *function* dans le code managé, bien que l'option [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) du compilateur soit spécifiée.  À la place, le compilateur émet l'avertissement C4793 et un message de continuation explicatif, puis compile la *function* dans le code natif.  Le message de continuation contient le texte de *reason* qui explique pourquoi la *function* ne peut pas être compilée dans `MSIL`.  
  
 Il s'agit d'un avertissement de niveau 1 émis lorsque vous spécifiez l'option `/clr:pure`du compilateur.  
  
 Le tableau suivant répertorie tous les messages de continuation potentiels.  
  
|Message de raison|Remarques|  
|-----------------------|---------------|  
|Les types de données alignés ne sont pas pris en charge dans le code managé|Le CLR doit être en mesure d'allouer autant de données que nécessaire, ce qui peut ne pas être possible si les données sont alignées avec les déclarations telles que [\_\_m128](../../cpp/m128.md) ou [aligner](../../cpp/align-cpp.md).|  
|Les fonctions utilisant "\_\_ImageBase" ne sont pas prises en charge dans le code managé|`__ImageBase` est un symbole d'éditeur de liens spécial utilisé en général uniquement par le code natif de bas niveau pour charger une DLL.|  
|Les varargs ne sont pas prises en charge par l'option '\/clr' du compilateur|Les fonctions natives ne peuvent pas appeler les fonctions managées qui ont des [listes d'arguments variables](../../misc/variable-argument-lists.md) \(varargs\) parce que les fonctions ont des spécifications de disposition en pile différentes.  Toutefois, si vous spécifiez l'option `/clr:pure` du compilateur, les listes d'arguments variables sont prises en charge parce que l'assembly peut contenir uniquement des fonctions gérées.  Pour plus d'informations, consultez [Code pur et vérifiable](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|  
|Le CLR 64 bits ne prend pas en charge les données déclarées avec le modificateur \_\_ptr32|Un pointeur doit être de la même taille qu'un pointeur natif sur la plateforme actuelle.  Pour plus d'informations, consultez [\_\_ptr32, \_\_ptr64](../../cpp/ptr32-ptr64.md).|  
|Le CLR 32 bits ne prend pas en charge les données déclarées avec le modificateur \_\_ptr64|Un pointeur doit être de la même taille qu'un pointeur natif sur la plateforme actuelle.  Pour plus d'informations, consultez [\_\_ptr32, \_\_ptr64](../../cpp/ptr32-ptr64.md).|  
|Un ou plusieurs intrinsèques ne sont pas pris en charge dans le code managé|Le nom de l'intrinsèque n'est pas disponible au moment où le message est émis.  Toutefois, un intrinsèque qui déclenche ce message représente en général une instruction machine de bas niveau.|  
|L'assembly natif inline \("\_\_asm"\) n'est pas pris en charge dans le code managé|[Le code assembleur inline](../../assembler/inline/asm.md) peut contenir du code natif arbitraire qui ne peut pas être géré.|  
|Un thunk de fonction virtuelle de non\-\_\_clrcall doit être compilé comme natif|Un thunk de fonction virtuelle non\-[\_\_clrcall](../../cpp/clrcall.md) doit utiliser une adresse non managée.|  
|Une fonction utilisant '\_setjmp' doit être compilée comme native|Le CLR doit être en mesure de contrôler l'exécution du programme.  Toutefois, la fonction [setjmp](../../cpp/using-setjmp-longjmp.md) contourne l'exécution normale du programme en enregistrant et restaurant des informations de bas niveau telles que les registres et l'état d'exécution.|  
  
## Exemple  
 L'exemple suivant génère l'erreur C4793.  
  
```  
// C4793.cpp  
// compile with: /c /clr /W3   
// processor: x86  
int asmfunc(void) {   // C4793, compiled as unmanaged, native code  
   __asm {  
      mov eax, 0  
   }  
}  
```  
  
  **warning C4793: 'asmfunc' : function is compiled as native code:**  
 **L'assembly natif inline \("\_\_asm"\) n'est pas pris en charge dans le code managé**   
## Exemple  
 L'exemple suivant génère l'erreur C4793.  
  
```  
// C4793_b.cpp  
// compile with: /c /clr /W3  
#include <setjmp.h>  
jmp_buf test_buf;  
  
void f() {  
   setjmp(test_buf);   // C4793 warning  
}  
```  
  
  **warning C4793: 'f' : function is compiled as native code:**  
 **Une fonction utilisant '\_setjmp' doit être compilée comme native**