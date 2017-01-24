---
title: "Fonctions de valeur cha&#238;ne en valeur num&#233;rique | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstoui64"
  - "_tcstoi64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "analyser, chaînes numériques"
  - "conversion de chaînes, en valeurs numériques"
ms.assetid: 11cbd9ce-033b-4914-bf66-029070e7e385
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctions de valeur cha&#238;ne en valeur num&#233;rique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

-   [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)  
  
-   [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)  
  
-   [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)  
  
-   [\_strtoi64, \_wcstoi64, \_strtoi64\_l, \_wcstoi64\_l](../c-runtime-library/reference/strtoi64-wcstoi64-strtoi64-l-wcstoi64-l.md)  
  
-   [\_strtoui64, \_wcstoui64, \_strtoui64\_l, \_wcstoui64\_l](../c-runtime-library/reference/strtoui64-wcstoui64-strtoui64-l-wcstoui64-l.md)  
  
## Notes  
 Chaque fonction de la famille **strtod** convertit une chaîne terminée par le caractère NULL en une valeur numérique.  Les fonctions disponibles sont répertoriées dans le tableau suivant.  
  
|Fonction|Description|  
|--------------|-----------------|  
|`strtod`|Convertissez la chaîne en valeur à virgule flottante double\-précision.|  
|`strtol`|Convertit la chaîne en entier long|  
|`strtoul`|Convertissez la chaîne en entier long non signé|  
|`_strtoi64`|Convertissez la chaîne en entier 64 bits `__int64`|  
|`_strtoui64`|Convertissez la chaîne en entier non signé 16 bits `__int64`.|  
  
 `wcstod`, `wcstol`, `wcstoul`, et `_wcstoi64` sont des versions à caractères larges de `strtod`, `strtol`, `strtoul`, et `_strtoi64`, respectivement.  L'argument de chaîne de chacune de ces fonctions à caractères étendus est une chaîne à caractères étendus ; chaque fonction se comporte de la même manière que son équivalent dont les caractères sont codés sur un octet sinon.  
  
 La fonction `strtod` accepte deux arguments : le premier est la chaîne d'entrée, le second est un pointeur vers le caractère qui met fin au processus de conversion.  `strtol`, `strtoul`, **\_strtoi64** et **\_strtoui64** prennent un troisième argument comme base de numéro à utiliser dans le processus de conversion.  
  
 La chaîne d'entrée est une séquence de caractères qui peuvent être interprétés comme une valeur numérique du type spécifié.  Chaque fonction arrête la lecture de la chaîne au premier caractère ne faisant apparemment pas partie d'un nombre.  Il peut s'agir du caractère null de fin.  Pour `strtol`, `strtoul`, `_strtoi64`, et `_strtoui64`, ce caractère de fin peut également être le premier chiffre supérieur ou égal à la base de numéro fournie par l'utilisateur.  
  
 Si le pointeur fourni par l'utilisateur vers un caractère de fin de conversion n'est pas défini à **NULL** au moment de l'appel, un pointeur vers le caractère qui a arrêté l'analyse est enregistré à la place.  Si aucune conversion ne peut être effectuée \(aucun chiffre valide n'a été trouvé ou une base non valide a été spécifiée\), la valeur du pointeur de chaîne est enregistrée à cette adresse.  
  
 `strtod` attend une chaîne au format suivant :  
  
 \[*espace blanc*\] \[*signe*\] \[`digits`\] \[**.**`digits`\] \[ {**d** &#124; **D** &#124; **e** &#124; **E**}\[*sign*\]`digits`\]  
  
 Un *espace blanc* peut se composer d'espaces ou de caractères de tabulations, qui sont ignorés ; *sign* est soit plus \(**\+**\) soit moins \(**–**\) ; et `digits` se composent d'un ou plusieurs chiffres décimaux.  Si aucun chiffre ne s'affiche avant le caractère de base, au moins un doit apparaître après le caractère de base.  Les nombres décimaux peuvent être suivis d'un exposant, qui comprend une lettre préliminaire \(**d**, **D**, **e**, ou **E**\) et éventuellement un entier signé.  Si ni une partie d'exposant ni un caractère de base n'apparaît, il suppose qu'un caractère de base suit le dernier chiffre dans la chaîne.  Le premier caractère qui ne correspond pas à ce formulaire arrête l'analyse.  
  
 Les fonctions `strtol`, `strtoul`, `_strtoi64`, et `_strtoui64` attendent une chaîne au format suivant :  
  
 \[*espace blanc*\] \[{**\+** &#124; **–**}\] \[**0** \[{ **x** &#124; **X** }\]\] \[`digits`\]  
  
 Si l'argument de base est compris entre 2 et 36, il est utilisé comme base du nombre.  Si la valeur est 0, les caractères initiaux référencés par le pointeur de fin de conversion sont utilisés pour déterminer la base.  Si le premier caractère est 0 et le deuxième caractère n'est pas « x » ou « X », la chaîne est interprétée en tant qu'entier octal ; sinon, elle est interprétée comme un nombre décimal.  Si le premier caractère est « 0 » et le deuxième caractère est « x » ou « X », la chaîne est interprétée comme un entier hexadécimal.  Si le premier caractère est compris entre « 1 » et « 9 », la chaîne est interprétée comme un entier décimal.  Les valeurs 10 à 35 sont assignées aux lettres « à » à « z » \(ou « À » à « Z »\) ; seules les lettres dont les valeurs assignées sont inférieures à *base* sont autorisées.  `strtoul` et `_strtoui64` autorisent un préfixe de signe plus \(**\+**\) ou moins \(**–**\) ; un signe moins au début indique que la valeur de retour est négative.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_NUMERIC` des paramètres régionaux ; consultez [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe **\_l** utilisent les paramètres régionaux courants pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe **\_l** sont identiques, sauf qu'elles utilisent le paramètre régional passé à la place.  
  
 Lorsque la valeur retournée par ces fonctions entraînent un débordement ou un sous\-écoulement, ou lorsque la conversion est impossible, les valeurs spéciales de cas sont retournées comme suit :  
  
|Fonction|Condition|Valeur de retour|  
|--------------|---------------|----------------------|  
|`strtod`|Dépassement de capacité|\+\/\- `HUGE_VAL`|  
|`strtod`|Sous\-écoulement ou aucune conversion|0|  
|`strtol`|\+ Débordement|**LONG\_MAX**|  
|`strtol`|\- Débordement|**LONG\_MIN**|  
|`strtol`|Sous\-écoulement ou aucune conversion|0|  
|`_strtoi64`|\+ Débordement|**\_I64\_MAX**|  
|`_strtoi64`|\- Débordement|**\_I64\_MIN**|  
|`_strtoi64`|Aucune conversion|0|  
|`_strtoui64`|Dépassement de capacité|**\_UI64\_MAX**|  
|`_strtoui64`|Aucune conversion|0|  
  
 **\_I64\_MAX**, \_**I64\_MIN**, et **\_UI64\_MAX** sont définis dans LIMITS.H.  
  
 `wcstod`, `wcstol`, `wcstoul`, `_wcstoi64`, et `_wcstoui64` sont des versions à caractères larges `strtod`, `strtol`, `strtoul`, `_strtoi64`, et `_strtoui64`, respectivement ; le pointeur vers un argument de fin de conversion dans chacune de ces fonctions à caractères étendus est une chaîne à caractères étendus.  Sinon, chacune de ces fonctions de caractères étendus se comporte de la même manière que son équivalent dont les caractères sont codés sur un octet.  
  
## Voir aussi  
 [Conversion de données](../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Prise en charge de la virgule flottante](../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)