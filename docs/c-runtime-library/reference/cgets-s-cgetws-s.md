---
title: "_cgets_s, _cgetws_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cgetws_s"
  - "_cgets_s"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_cgets_s"
  - "cgets_s"
  - "cgetws_s"
  - "_cgetws_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cgets_s (fonction)"
  - "_cgetws_s (fonction)"
  - "cget_s (fonction)"
  - "cgetws_s (fonction)"
  - "console, obtenir des chaînes de"
  - "chaînes (C++), obtenir de la console"
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _cgets_s, _cgetws_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient une chaîne de caractères à partir de la console.  Ces versions de [\_cgets et \_cgetws](../../c-runtime-library/cgets-cgetws.md) intègrent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
errno_t _cgets_s(   
   char *buffer,  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
errno_t _cgetws_s(  
   wchar_t *buffer  
   size_t numberOfElements,  
   size_t *pSizeRead  
);  
template <size_t size>  
errno_t _cgets_s(   
   char (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
template <size_t size>  
errno_t _cgetws_s(  
   wchar_t (&buffer)[size],  
   size_t *pSizeRead  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `buffer`  
 Emplacement de stockage des données.  
  
 \[in\] `numberOfElements`  
 Taille de la mémoire tampon en caractères larges ou codés sur un octet, qui correspond aussi au nombre maximal de caractères à lire.  
  
 \[in\] `pSizeRead`  
 Nombre de caractères véritablement lus.  
  
## Valeur de retour  
 La valeur de retour est égale à zéro en cas de réussite ; sinon, un code d'erreur est retourné en cas de défaillance.  
  
### Conditions d'erreur  
  
|`buffer`|`numberOfElements`|`pSizeRead`|Retourner|Contenu de `buffer`|  
|--------------|------------------------|-----------------|---------------|-------------------------|  
|`NULL`|tous|tous|`EINVAL`|Non applicable|  
|non `NULL`|zéro|tous|`EINVAL`|non modifié|  
|non `NULL`|tous|`NULL`|`EINVAL`|chaîne de longueur nulle|  
  
## Notes  
 `_cgets_s` et `_cgetws_s` lisent une chaîne à partir de la console et copient la chaîne \(avec une marque de fin null\) dans `buffer`.  `_cgetws_s` est la version à caractères larges de la fonction ; hormis la taille de caractères, le comportement de ces deux fonctions est identique.  La taille maximale de la chaîne à lire est passée en tant que paramètre `numberOfElements`.  Cette taille doit inclure un caractère supplémentaire pour le caractère null de fin.  Le nombre réel de caractères lus est placé dans `pSizeRead`.  
  
 Si une erreur se produit pendant l'opération ou lors de la validation des paramètres, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` prend la valeur `EINVAL` et `EINVAL` est retourné.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement, ce qui évite ainsi d'avoir à spécifier un argument de taille, et elles peuvent remplacer automatiquement les fonctions plus anciennes et moins sécurisées par leurs équivalents plus récents et sécurisés.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_cgetts_s`|`_cgets_s`|`_cgets_s`|`_cgetws_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_cgets_s`|\<conio.h\>|  
|`_cgetws_s`|\<conio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)