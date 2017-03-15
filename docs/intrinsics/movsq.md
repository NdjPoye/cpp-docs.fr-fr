---
title: "__movsq | Microsoft Docs"
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
  - "__movsq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__movsq intrinsèque"
  - "rep movsq, instruction"
  - "movsq, instruction"
ms.assetid: be116a6e-2176-4ca4-93b1-9ccf3e7e7835
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __movsq
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère une instruction répétée de chaîne de déplacement \(`rep movsq`\).  
  
## Syntaxe  
  
```  
void __movsq(   
   unsigned char* Dest,   
   unsigned char* Source,   
   size_t Count   
);  
```  
  
#### Paramètres  
 \[out\] `Dest`  
 la destination de l'opération.  
  
 \[in\] `Source`  
 La source de l'opération.  
  
 \[in\] `Count`  
 le nombre de mots quadruples à copier.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__movsq`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Le résultat est que les premiers mots quadruples d' `Count` entrées figurant dans `Source` sont copiés dans la chaîne d' `Dest` .  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// movsq.cpp  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsq)  
  
int main()  
{  
    unsigned __int64 a1[10];  
    unsigned __int64 a2[10] = {950, 850, 750, 650, 550, 450, 350, 250,  
                               150, 50};  
    __movsq(a1, a2, 10);  
  
    for (int i = 0; i < 10; i++)  
       printf_s("%d ", a1[i]);  
    printf_s("\n");  
}  
```  
  
  **950 850 750 650 550 450 350 250 150 50**    
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)