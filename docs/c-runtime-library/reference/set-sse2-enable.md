---
title: "_set_SSE2_enable | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_SSE2_enable"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_SSE2_enable"
  - "set_SSE2_enable"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_SSE2_enable (fonction)"
  - "instructions des extensions Streaming SIMD 2"
  - "set_SSE2_enable (fonction)"
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_SSE2_enable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Active ou désactive l'utilisation des instructions [Extensions Streaming SIMD 2](http://msdn.microsoft.com/fr-fr/f98440eb-73a9-4f96-b203-ac41bb6701ea) \(SSE2\) dans les routines mathématiques CRT. \(Cette fonction n'est pas disponible sur les architectures x64 car SSE2 est activé par défaut.\)  
  
## Syntaxe  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### Paramètres  
 `flag`  
 1 pour activer l'implémentation SSE2 ; 0 pour désactiver l'implémentation SSE2.  Par défaut, l'implémentation SSE2 est activée sur des processeurs qui la prennent en charge.  
  
## Valeur de retour  
 Une valeur différente de zéro si l'implémentation SSE2 est activée ; zéro si l'implémentation SSE2 est désactivée.  
  
## Notes  
 Les fonctions suivantes ont des implémentations SSE2 qui peuvent être activées à l'aide de `_set_SSE2_enable`:  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [log](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [pow](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 Les implémentations SSE2 de ces fonctions peuvent donner des réponses légèrement différentes des implémentations par défaut, car les valeurs SSE2 intermédiaires sont des quantités à virgule flottante 64 bits alors que les valeurs intermédiaires d'implémentation par défaut sont des quantités à virgule flottante 80\-bit.  
  
> [!NOTE]
>  Si vous utilisez l'option du compilateur [\/Oi \(Générer des fonctions intrinsèques\)](../../build/reference/oi-generate-intrinsic-functions.md) pour compiler le projet, il peut se passer que `_set_SSE2_enable` n'a aucun effet.  L'option du compilateur `/Oi` donne au compilateur l'autorité pour utiliser les intrinsèques pour remplacer les appels CRT ; ce comportement remplace l'effet de `_set_SSE2_enable`.  Si vous souhaitez vous assurer que `/Oi` ne remplace pas `_set_SSE2_enable`, utilisez `/Oi-` pour compiler votre projet.  Cela peut également être recommandé lorsque vous utilisez d'autres commutateurs de compilation qui impliquent `/Oi`.  
  
 L'implémentation SSE2 est utilisée uniquement si toutes les exceptions sont masquées.  Utilisez [\_control87, \_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) pour masquer des exceptions.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_SSE2_enable`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **Sortie**  
  
 `SSE2 enabled.`  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md)