---
title: "Mappages de types de donn&#233;es | Microsoft Docs"
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
  - "_TXCHAR"
  - "_TUCHAR"
  - "_TINT"
  - "_TSCHAR"
  - "_TCHAR"
  - "TCHAR::H"
  - "TCHAR"
  - "_T"
  - "_TEXT"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_T (type)"
  - "_TCHAR (type)"
  - "_TEXT (type)"
  - "_TINT (type)"
  - "_TSCHAR (type)"
  - "_TUCHAR (type)"
  - "_TXCHAR (type)"
  - "types de données de texte générique"
  - "T (type)"
  - "TCHAR (type)"
  - "types de données TCHAR.H, mappages définis dans"
  - "TEXT (type)"
  - "TINT (type)"
  - "TSCHAR (type)"
  - "TUCHAR (type)"
  - "TXCHAR (type)"
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Mappages de types de donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces mappings de type de données sont définies dans TCHAR.H et varient selon que la constante`_UNICODE` ou `_MBCS` a été défini dans votre programme.  
  
 Pour plus d'informations, consultez [Utilisation de types de données de TCHAR.H avec le code de \_MBCS](../text/using-tchar-h-data-types-with-mbcs-code.md).  
  
### Mappages de types de données de texte générique  
  
|Texte générique<br /><br /> Nom du type de données|SBCS \(\_UNICODE,<br /><br /> \_MBCS not<br /><br /> défini\)|\_MBCS<br /><br /> défini|\_UNICODE<br /><br /> défini|  
|------------------------------------------------|---------------------------------------------------|-----------------------|--------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|  
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|  
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` ou `_TEXT`|Aucun effet \(supprimé par le préprocesseur\)|Aucun effet \(supprimé par le préprocesseur\)|`L` \(convertit le caractère ou la chaîne suivant\(e\) en son équivalent Unicode\)|  
  
## Voir aussi  
 [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md)   
 [Mappage des constantes et des variables globales](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Mappages de routine](../c-runtime-library/routine-mappings.md)   
 [Programme de texte générique, exemple](../c-runtime-library/a-sample-generic-text-program.md)   
 [Utilisation des mappages de texte générique](../c-runtime-library/using-generic-text-mappings.md)