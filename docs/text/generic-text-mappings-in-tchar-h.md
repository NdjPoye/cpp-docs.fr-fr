---
title: "Mappages de texte g&#233;n&#233;rique dans Tchar.h | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ""tchar.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jeux de caractères (C++), mappages de texte générique"
  - "mappages de texte générique (C++)"
  - "mapper du texte générique"
  - "mappages (C++), TCHAR.H"
  - "MBCS (C++), mappages de texte générique"
  - "types de données TCHAR.H, mapper"
  - "Unicode (C++), mappages de texte générique"
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
caps.latest.revision: 12
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Mappages de texte g&#233;n&#233;rique dans Tchar.h
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour faciliter le transport de code pour une utilisation internationale, la bibliothèque Runtime [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] fournit des mappages de texte générique spécifiques à [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] pour de nombreux types de données, routines et autres objets.  Vous pouvez utiliser ces mappages, qui sont définis dans Tchar.h, pour écrire du code générique qui peut être compilé sur un octet, sur plusieurs octets ou en [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)], en fonction d'une constante de manifeste que vous définissez en utilisant une instruction `#define`.  Les mappages de texte générique sont des extensions [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] qui ne sont pas compatibles [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)].  
  
 En utilisant le fichier Tchar.h, vous pouvez générer des applications codées sur un octet, MBCS et [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)] à partir des mêmes sources.  Tchar.h définit des macros \(avec le préfixe `_tcs`\) qui correspondent aux fonctions `str`, `_mbs` ou `wcs`, selon les besoins et avec les définitions de préprocesseur appropriées.  Pour générer une application MBCS, définissez le symbole `_MBCS`.  Pour générer une application [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)], définissez le symbole `_UNICODE`.  Pour générer une application codée sur un octet, ne définissez rien \(valeur par défaut\).  Par défaut, `_MBCS` est défini pour les applications MFC.  
  
 Le type de données `_TCHAR` est défini de façon conditionnelle dans Tchar.h.  Si le symbole `_UNICODE` est défini pour votre génération, `_TCHAR` est défini sous la forme `wchar_t` ; sinon, pour les générations MBCS et celles codées sur un octet, il est défini en tant que `char`. \(`wchar_t`, type de données à caractère élargi Unicode de base, est l'équivalent 16 bits d'un `char` 8 bits signé.\) Pour des applications internationales, utilisez la famille de fonctions `_tcs`, qui fonctionne en unités `_TCHAR` et non en octets.  Par exemple, `_tcsncpy` copie `n``_TCHARs`, et non `n` octets.  
  
 Dans la mesure où certaines fonctions de gestion de chaîne SBCS \(Single Byte Character Set\) utilisent des paramètres `char*` \(signés\), un avertissement du compilateur d'incompatibilité de type se produit lors de la définition de `_MBCS`.  Il existe trois façons d'éviter cet avertissement :  
  
1.  Utilisez les thunks de la fonction inline de type sécurisé dans Tchar.h.  Il s'agit du comportement par défaut.  
  
2.  Utilisez les macros directes dans Tchar.h en définissant `_MB_MAP_DIRECT` sur la ligne de commande.  Si vous utilisez ces macros, vous devez faire correspondre les types manuellement.  Il s'agit de la méthode la plus sûre, mais elle n'est pas type\-safe.  
  
3.  Utilisez les thunks de type sécurisé de la fonction de bibliothèque liée statiquement dans Tchar.h.  Pour cela, définissez la constante `_NO_INLINING` sur la ligne de commande.  Il s'agit de la méthode la plus lente, mais la plus type\-safe.  
  
### Directives du préprocesseur pour les mappages de texte générique  
  
|\# define|Version compilée|Exemple|  
|---------------|----------------------|-------------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)] \(caractère élargi\)|`_tcsrev` correspond à `_wcsrev`|  
|`_MBCS`|Caractère multioctets|`_tcsrev` correspond à `_mbsrev`|  
|Aucun \(la valeur par défaut n'est définie ni sur `_UNICODE`, ni sur `_MBCS`\)|SBCS \([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)]\)|`_tcsrev` correspond à `strrev`|  
  
 Par exemple, la fonction de texte générique `_tcsrev`, qui est définie dans Tchar.h, correspond à `_mbsrev` si vous avez défini `_MBCS` dans votre programme, ou à `_wcsrev` si vous avez défini `_UNICODE`.  Sinon, `_tcsrev` correspond à `strrev`.  Pour des besoins de programmation, Tchar.h fournit d'autres mappages de type de données, mais `_TCHAR` est le plus utile.  
  
### Mappages de types de données de texte générique  
  
|Texte de générique<br /><br /> Nom du type de données|\_UNICODE &<br /><br /> Non défini par \_UNICODE & \_MBCS|\_MBCS<br /><br /> \(défini par\)|\_UNICODE<br /><br /> \(défini par\)|  
|---------------------------------------------------|-------------------------------------------------------|-------------------------------|----------------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`unsigned int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` ou `_TEXT`|Aucun effet \(supprimé par le préprocesseur\)|Aucun effet \(supprimé par le préprocesseur\)|`L` \(convertit le caractère ou la chaîne suivant\(e\) en son équivalent [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)]\)|  
  
 Pour obtenir une liste complète des mappages de texte générique des routines, variables et autres objets, consultez [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md) dans la référence de la bibliothèque Runtime.  
  
> [!NOTE]
>  N'utilisez pas la famille de fonctions `str` avec des chaînes Unicode, qui peuvent contenir des octets null incorporés.  De même, n'utilisez pas la famille de fonctions `wcs` avec des chaînes MBCS \(ou SBCS\).  
  
 Les fragments de code suivants montrent comment utiliser `_TCHAR` et `_tcsrev` pour le mappage aux modèles MBCS, [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)] et SBCS.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Si `_MBCS` a été défini, le préprocesseur mappe ce fragment à ce code :  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Si `_UNICODE` a été défini, le préprocesseur mappe ce fragment à ce code :  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Si ni `_MBCS` ni `_UNICODE` n'ont été définis, le préprocesseur mappe ce fragment en code [!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)] codé sur un octet, comme suit :  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 Vous pouvez donc écrire, maintenir et compiler un fichier de code source unique à exécuter avec des routines qui sont spécifiques à ces trois genres de jeux de caractères.  
  
## Voir aussi  
 [Texte et chaînes](../text/text-and-strings-in-visual-cpp.md)   
 [Utilisation de types de données TCHAR.H avec \_MBCS](../text/using-tchar-h-data-types-with-mbcs-code.md)