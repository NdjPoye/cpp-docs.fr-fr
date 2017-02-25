---
title: "Directives pragma et mot cl&#233; _Pragma | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#pragma"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "directives #pragma, C/C++"
  - "__pragma (mot clé)"
  - "directives pragma (#pragma)"
  - "directives pragma, C/C++"
  - "pragmas"
  - "pragmas, C/C++"
  - "préprocesseur"
  - "préprocesseur, pragmas"
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Directives pragma et mot cl&#233; _Pragma
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les directives pragma spécifient des fonctionnalités de compilateur spécifiques à l'ordinateur ou au système d'exploitation.  Le mot clé `__pragma`, qui est spécifique au compilateur Microsoft, vous permet de coder des directives pragma dans des définitions de macros.  
  
## Syntaxe  
  
```  
  
      #pragma token-string  
__pragma(token-string)  
```  
  
## Notes  
 Chaque implémentation de C et C\+\+ prend en charge des fonctionnalités spécifiques de son ordinateur hôte ou de son système d'exploitation.  Certains programmes, par exemple, doivent exercer un contrôle précis des zones de mémoire où les données sont placées, ou contrôler la façon dont certaines fonctions reçoivent les paramètres.  Les directives `#pragma` permettent à chaque compilateur d'offrir des fonctionnalités propres aux ordinateurs et aux systèmes d'exploitation tout en conservant une compatibilité globale avec les langages C et C\+\+.  
  
 Les pragmas sont spécifiques à l'ordinateur ou au système d'exploitation, par définition, et sont généralement différents pour chaque compilateur.  Les pragmas peuvent être utilisés dans les instructions conditionnelles pour fournir de nouvelles fonctionnalités de préprocesseur ou pour fournir des informations définies par l'implémentation au compilateur.  
  
 `token-string` est une série de caractères qui fournit à un compilateur spécifique l'instruction et les arguments, le cas échéant.  Le signe dièse \(**\#**\) doit être le premier caractère autre qu'un espace blanc sur la ligne contenant le pragma ; les espaces blancs peuvent séparer le signe dièse du mot "pragma".  Après `#pragma`, saisissez un texte que le traducteur peut analyser en tant que jetons de prétraitement.  L'argument de `#pragma` est soumis à une expansion macro.  
  
 Si le compilateur recherche un pragma qu'il ne reconnaît pas, il émet un avertissement et continue la compilation.  
  
 Les compilateurs Microsoft C et C\+\+ reconnaissent les pragmas suivants :  
  
||||  
|-|-|-|  
|[alloc\_text](../preprocessor/alloc-text.md)|[auto\_inline](../preprocessor/auto-inline.md)|[bss\_seg](../preprocessor/bss-seg.md)|  
|[check\_stack](../preprocessor/check-stack.md)|[code\_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|  
|[component](../preprocessor/component.md)|[conform](../preprocessor/conform.md) <sup>1</sup>|[const\_seg](../preprocessor/const-seg.md)|  
|[data\_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect\_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv\_access](../preprocessor/fenv-access.md)|[float\_control](../preprocessor/float-control.md)|[fp\_contract](../preprocessor/fp-contract.md)|  
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include\_alias](../preprocessor/include-alias.md)|  
|[init\_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline\_depth](../preprocessor/inline-depth.md)|[inline\_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[loop](../preprocessor/loop.md) <sup>1</sup>|[make\_public](../preprocessor/make-public.md)|  
|[managed](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers\_to\_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|  
|[pop\_macro](../preprocessor/pop-macro.md)|[push\_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|  
|[runtime\_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict\_gs\_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|  
|[warning](../preprocessor/warning.md)|||  
  
 1.  Pris en charge uniquement par le compilateur C\+\+.  
  
## Pragmas et options du compilateur  
 Certains pragmas fournissent les mêmes fonctionnalités que les options du compilateur.  Lorsqu'un pragma est rencontré dans le code source, il remplace le comportement spécifié par l'option du compilateur.  Par exemple, si vous avez spécifié [\/Zp8](../build/reference/zp-struct-member-alignment.md), vous pouvez remplacer ce paramètre de compilateur pour les sections spécifiques de code par [pack](../preprocessor/pack.md):  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## Mot clé \_\_pragma\(\)  
 **Section spécifique à Microsoft**  
  
 Le compilateur prend également en charge le mot clé `__pragma`, qui a les mêmes fonctionnalités que la directive `#pragma`, mais qui peut être utilisé inline dans une définition de macro.  La directive `#pragma` ne peut pas être utilisée dans une définition de macro, car le compilateur interprète le signe dièse \(\#\) de la directive en tant qu'[opérateur de transformation en chaîne \(\#\)](../preprocessor/stringizing-operator-hash.md).  
  
 L'exemple de code suivant illustre l'utilisation du mot clé `__pragma` dans une macro.  Ce code est extrait de l'en\-tête mfcdual.h de l'exemple CDUAL dans « Exemples de prise en charge COM du compilateur » :  
  
```  
#define CATCH_ALL_DUAL \  
CATCH(COleException, e) \  
{ \  
_hr = e->m_sc; \  
} \  
AND_CATCH_ALL(e) \  
{ \  
__pragma(warning(push)) \  
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \  
AFX_MANAGE_STATE(pThis->m_pModuleState); \  
__pragma(warning(pop)) \  
_hr = DualHandleException(_riidSource, e); \  
} \  
END_CATCH_ALL \  
return _hr; \  
```  
  
 **Fin de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Référence du préprocesseur C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Pragmas C](../c-language/c-pragmas.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)