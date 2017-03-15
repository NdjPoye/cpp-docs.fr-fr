---
title: "Utilisation des mappages de texte g&#233;n&#233;rique | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_UNICODE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_MBCS (type de données)"
  - "_T (type)"
  - "_TCHAR (type)"
  - "_TEXT (type)"
  - "_TINT (type)"
  - "_TSCHAR (type)"
  - "_TUCHAR (type)"
  - "_TXCHAR (type)"
  - "_UNICODE (constante)"
  - "types de données de texte générique"
  - "mappages de texte générique"
  - "mappages, texte générique"
  - "MBCS (type de données)"
  - "T (type)"
  - "TCHAR (type)"
  - "types de données TCHAR.H, mappages définis dans"
  - "TEXT (type)"
  - "TINT (type)"
  - "TSCHAR (type)"
  - "TUCHAR (type)"
  - "TXCHAR (type)"
  - "UNICODE (constante)"
ms.assetid: 2848121c-e51f-4b9b-a2e6-833ece4b0cb3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Utilisation des mappages de texte g&#233;n&#233;rique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Pour faciliter le développement logiciel pour de nombreux marchés internationaux, la bibliothèque Runtime Microsoft fournit des mappingsde textes génériques spécifiques à Microsoft pour de nombreux types de données, routines et autres objets.  Ces mappings sont définis dans TCHAR.H.  Vous pouvez utiliser ces mappings d'étiquette pour écrire du code générique qui peut être compilé pour chacun des trois types de jeux de caractères : ASCII \(SBCS\), MBCS, ou Unicode, en fonction d'une constante explicite que vous définissez à l'aide d'une instruction `#define`.  Les mappings de texte générique sont des extensions  Microsoft qui ne sont pas compatibles pour ANSI.  
  
### Directives du préprocesseur pour les mappages de texte générique  
  
|\#define|Version compilée|Exemple|  
|--------------|----------------------|-------------|  
|`_UNICODE`|Tout caractère large|`_tcsrev` correspond à `_wcsrev`|  
|`_MBCS`|Caractère multioctets|`_tcsrev` correspond à `_mbsrev`|  
|Aucun \(la valeur par défaut n'est définie ni sur `_UNICODE`, ni sur `_MBCS`\)|SBCS \(ASCII\)|\<languageKeyword\>1\_tcsrev 2\<\/languageKeyword\>1 map avec \<languageKeyword\>3strrev4\<\/languageKeyword\>|  
  
 Par exemple, la fonction de texte générique `_tcsrev`, qui est définie dans Tchar.h, correspond à `mbsrev` si vous avez défini `MBCS` dans votre programme, ou à `_wcsrev`  si vous avez défini `_UNICODE` .  Sinon, `_tcsrev`  correspond à `strrev`.  
  
 Le type de données textuelles générique `_TCHAR`, également défini dans TCHAR.H, est mappé en type `char` si `_MBCS` est défini, en `wchar_t` si `_UNICODE` est défini, et en type `char` si aucune des constantes n'est définie.  Pour des besoins de programmation, Tchar.h fournit d'autres mappages de type de données, mais `_TCHAR` est le type plus utile.  
  
### Mappages de types de données de texte générique  
  
|Mapping de types de données textuelles générique|SBCS \(\_UNICODE, \_MBCS pas définit\)|\_MBCS défini|\_UNICODE défini|  
|------------------------------------------------------|--------------------------------------------|-------------------|----------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` ou `_TEXT`|Aucun effet \(supprimé par le préprocesseur\)|Aucun effet \(supprimé par le préprocesseur\)|`L` \(convertit le caractère ou la chaîne suivant\(e\) en son équivalent Unicode\)|  
  
 Pour obtenir la liste complète des mappings de textes génériques des routines, des variables, et d'autres objets, consultez [Mappings de texte générique](../c-runtime-library/generic-text-mappings.md).  
  
 Les fragments de code suivants montrent comment utiliser `_TCHAR` et `_tcsrev` pour le mapping des MBCS, Unicode,  et modèles SBCS.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Si `MBCS` a bien été défini, le préprocesseur mappe le fragment précédent au code suivant :  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Si `_UNICODE` a bien été défini, le préprocesseur mappe le même fragment au code suivant :  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Si ni `_MBCS` ni `_UNICODE` n'ont été définis, le préprocesseur mappe ce fragment en code ASCII sur un octet, comme suit :  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 Vous pouvez donc écrire, maintenir et compiler un fichier de code source unique à exécuter avec des routines qui sont spécifiques à ces trois jeux de caractères.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md)   
 [Mappages de types de données](../c-runtime-library/data-type-mappings.md)   
 [Mappage des constantes et des variables globales](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Mappages de routine](../c-runtime-library/routine-mappings.md)   
 [Programme de texte générique, exemple](../c-runtime-library/a-sample-generic-text-program.md)