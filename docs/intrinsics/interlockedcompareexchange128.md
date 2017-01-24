---
title: "_InterlockedCompareExchange128 | Microsoft Docs"
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
  - "_InterlockedCompareExchange128_cpp"
  - "_InterlockedCompareExchange128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cmpxchg16b, instruction"
  - "_InterlockedCompareExchange128, intrinsèque"
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedCompareExchange128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Effectue un 128 bits verrouillées comparent et échangent.  
  
## Syntaxe  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### Paramètres  
 \[in, out\]  `Destination`  
 Pointeur vers la destination, qui est un tableau de deux entiers 64 bits considérés comme un champ 128 bits.  Les données de destination doit être l'octet 16 aligné pour éviter une erreur de protection générale.  
  
 \[in\] `ExchangeHigh`  
 Entier 64 bits qui peut être permuté avec la partie élevée de la destination.  
  
 \[in\] `ExchangeLow`  
 Entier 64 bits qui peut être permuté avec la partie inférieure de la destination.  
  
 \[in, out\]  `ComparandResult`  
 Pointeur vers un tableau de deux entiers 64 bits \(considérés comme un champ 128 bits\) à comparer à la destination.  Lors de la sortie, cela est remplacée par la valeur d'origine de la destination.  
  
## Valeur de retour  
 1 si le terme de comparaison 128 bits égale à la valeur d'origine de la destination.  `ExchangeHigh` et `ExchangeLow` remplacent la destination 128 bits.  
  
 0 si le terme de comparaison n'a pas la valeur d'origine de la destination.  La valeur de la destination est inchangée et la valeur du terme de comparaison est remplacée par la valeur de la destination.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque génère des instructions d'`cmpxchg16b` \(avec le préfixe d' `lock` \) d'effectuer un verrouillé 128 bits comparent et échangent.  Les premières versions du matériel 64 bits de AMD ne prennent pas en charge cette instruction.  Pour vérifier la prise en charge du matériel pour l'instruction d' `cmpxchg16b`, appelez l'intrinsèque de `__cpuid` avec `InfoType=0x00000001 (standard function 1)`.  Les plateformes 13 bits d' `CPUInfo[2]`\(ECX\) est 1 si l'instruction est prise en charge.  
  
> [!NOTE]
>  la valeur d' `ComparandResult` est toujours remplacée.  Après l'instruction d' `lock` , cette intrinsèque copie immédiatement la valeur initiale d' `Destination` à `ComparandResult`.  Pour cette raison, `ComparandResult` et `Destination` doivent indiquer les emplacements de mémoire séparés pour éviter un comportement inattendu.  
  
 Bien que vous puissiez utiliser `_InterlockedCompareExchange128` pour la synchronisation des threads de bas niveau, vous n'avez pas besoin de synchroniser plus de 128 bits si vous pouvez utiliser des fonctions plus petites de synchronisation \(telles que les autres intrinsèques d' `_InterlockedCompareExchange` \).  Utilisez `_InterlockedCompareExchange128` si vous souhaitez accéder atomique à une valeur 128 bits en mémoire.  
  
 Si vous exécutez le code qui utilise cette intrinsèque sur le matériel qui ne prend pas en charge l'instruction d' `cmpxchg16b` , les résultats sont imprévisibles.  
  
 Cette routine est disponible uniquement comme intrinsèque.  
  
## Exemple  
 Cet exemple utilise `_InterlockedCompareExchange128` pour remplacer le mot élevé d'un tableau de deux entiers 64 bits par la somme de ses mots de substitut étendu et terre et pour incrémenter le bas mot.  L'accès au tableau de BigInt.Int pour les utilisations atomiques, mais de cet exemple un thread unique et ignore le verrouillage pour plus de simplicité.  
  
```  
// cmpxchg16b.c  
// processor: x64  
// compile with: /EHsc /O2  
#include <stdio.h>  
#include <intrin.h>  
  
typedef struct _LARGE_INTEGER_128 {  
    __int64 Int[2];  
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;  
  
volatile LARGE_INTEGER_128 BigInt;  
  
// This AtomicOp() function atomically performs:  
//   BigInt.Int[1] += BigInt.Int[0]  
//   BigInt.Int[0] += 1  
void AtomicOp ()  
{  
    LARGE_INTEGER_128 Comparand;  
    Comparand.Int[0] = BigInt.Int[0];  
    Comparand.Int[1] = BigInt.Int[1];  
    do {  
        ; // nothing  
    } while (_InterlockedCompareExchange128(BigInt.Int,  
                                            Comparand.Int[0] + Comparand.Int[1],  
                                            Comparand.Int[0] + 1,  
                                            Comparand.Int) == 0);  
}  
  
// In a real application, several threads contend for the value  
// of BigInt.  
// Here we focus on the compare and exchange for simplicity.  
int main(void)  
{  
   BigInt.Int[1] = 23;  
   BigInt.Int[0] = 11;  
   AtomicOp();  
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",  
      BigInt.Int[1],BigInt.Int[0]);  
}  
```  
  
  **BigInt.Int \[1\] \= 34, BigInt.Int \[0\] \= 12**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [\_InterlockedCompareExchange Intrinsic Functions](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)