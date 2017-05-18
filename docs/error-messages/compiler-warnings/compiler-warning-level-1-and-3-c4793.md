---
title: Compilateur avertissement (niveaux 1 et 3) C4793 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4793
dev_langs:
- C++
helpviewer_keywords:
- C6634
- C6635
- C6640
- C6630
- C6639
- C6636
- C6638
- C6631
- C6637
- C4793
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: a217d2074affa1598aef93882fb299c6fcdef5a6
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-and-3-c4793"></a>Avertissement du compilateur (niveaux 1 et 3) C4793
'fonction' : fonction est compilée en code natif : 'raison'  
  
 Le compilateur ne peut pas compiler *fonction* dans du code managé, bien que le [/clr](../../build/reference/clr-common-language-runtime-compilation.md) option du compilateur est spécifiée. Au lieu de cela, le compilateur émet l’avertissement C4793 et un message de continuation explicatif, puis compile *fonction* en code natif. Le message de continuation contient le *raison* texte qui explique pourquoi *fonction* ne peut pas être compilé en `MSIL`.  
  
 Il s’agit d’un avertissement de niveau 1 lorsque vous spécifiez la `/clr:pure` option du compilateur.  Le **/CLR : pure** option du compilateur est déconseillée dans Visual Studio 2015.  
  
 Le tableau suivant répertorie tous les messages de continuation potentiels.  
  
|Message de raison|Notes|  
|--------------------|-------------|  
|Types de données alignés ne sont pas pris en charge dans le code managé|Le CLR doit être en mesure d’allouer des données en fonction des besoins, qui ne peut pas être possible si les données sont alignées avec les déclarations telles que [__m128](../../cpp/m128.md) ou [aligner](../../cpp/align-cpp.md).|  
|Les fonctions qui utilisent '__ImageBase' ne sont pas pris en charge dans le code managé|`__ImageBase`est un symbole d’éditeur de liens spécial qui est généralement utilisé uniquement par le code natif de bas niveau pour charger une DLL.|  
|varargs ne sont pas pris en charge par le « / clr' option du compilateur|Fonctions natives ne peuvent pas appeler les fonctions managées qui ont [listes d’arguments variables](../../cpp/functions-with-variable-argument-lists-cpp.md) (varargs) parce que les fonctions ont des spécifications de disposition de pile différentes. Toutefois, si vous spécifiez la `/clr:pure` option du compilateur, les listes sont pris en charge, car l’assembly peut contenir uniquement des fonctions gérées variable d’arguments. Pour plus d’informations, consultez [Code pur et vérifiable (C++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|  
|Le CLR 64 bits ne prend pas en charge les données déclarées avec le modificateur __ptr32|Un pointeur doit être la même taille qu’un pointeur natif sur la plateforme actuelle. Pour plus d’informations, consultez [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|  
|Le CLR 32 bits ne prend pas en charge les données déclarées avec le modificateur __ptr64|Un pointeur doit être la même taille qu’un pointeur natif sur la plateforme actuelle. Pour plus d’informations, consultez [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|  
|Un ou plusieurs intrinsèques ne sont pas pris en charge dans le code managé|Le nom de la fonction intrinsèque n’est pas disponible au moment où que le message est émis. Toutefois, un intrinsèque qui déclenche ce message généralement représente une instruction machine de bas niveau.|  
|L’assembly inline natif ('__asm') n’est pas pris en charge dans le code managé|[Le code assembleur inline](../../assembler/inline/asm.md) peut contenir du code natif arbitraire qui ne peut pas être géré.|  
|Un thunk de fonction virtuelle non __clrcall doit être compilé comme code natif|Non -[__clrcall](../../cpp/clrcall.md) thunk de fonction virtuelle doit utiliser une adresse non managée.|  
|Une fonction utilisant '_setjmp' doit être compilée comme code natif|Le CLR doit être en mesure de contrôler l’exécution du programme. Toutefois, le [setjmp](../../cpp/using-setjmp-longjmp.md) fonction contourne l’exécution normale du programme en enregistrant et restaurant des informations de bas niveau telles que les registres et l’état d’exécution.|  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4793.  
  
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
  
```Output  
warning C4793: 'asmfunc' : function is compiled as native code:  
        Inline native assembly ('__asm') is not supported in managed code  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4793.  
  
```  
// C4793_b.cpp  
// compile with: /c /clr /W3  
#include <setjmp.h>  
jmp_buf test_buf;  
  
void f() {  
   setjmp(test_buf);   // C4793 warning  
}  
```  
  
```Output  
warning C4793: 'f' : function is compiled as native code:  
        A function using '_setjmp' must be compiled as native  
```
