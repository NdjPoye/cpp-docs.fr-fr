---
title: "Caract&#232;res du champ de type printf | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf (fonction), champs de spécification de format"
  - "printf (fonction), caractères du champ de type"
ms.assetid: 699cb438-cd14-402e-9f81-c7a32acc3317
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Caract&#232;res du champ de type printf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans une spécification de format, le caractère `type` est un spécificateur de conversion qui précise si l'argument correspondant doit être interprété comme un caractère, une chaîne, un pointeur, un entier ou un nombre à virgule flottante.  Le caractère `type` est le seul champ de spécification de format obligatoire ; il apparaît après tous les champs facultatifs.  
  
 Les arguments qui suivent la chaîne de format sont interprétés en fonction du caractère `type` correspondant et du préfixe de [taille](../c-runtime-library/size-specification.md) facultatif.  Les conversions pour les types de caractères `char` et `wchar_t` sont spécifiées à l'aide de `c` ou `C`, tandis que les chaînes de caractères codés sur un octet et multioctets ou à caractères larges sont spécifiées à l'aide de `s` ou `S`, selon la fonction de mise en forme utilisée.  Les arguments de caractère et de chaîne spécifiés à l'aide de `c` et `s` sont interprétés en tant que `char` et `char*` par les fonctions de famille `printf` ou en tant que `wchar_t` et `wchar_t*` par les fonctions de famille `wprintf`.  Les arguments de caractère et de chaîne spécifiés à l'aide de `C` et `S` sont interprétés en tant que `wchar_t` et `wchar_t*` par les fonctions de famille `printf` ou en tant que `char` et `char*` par les fonctions de famille `wprintf`.  
  
 Les types entier tels que `short`, `int`, `long`, `long long`, ainsi que leurs variantes `unsigned`, sont spécifiés à l'aide de `d`, `i`, `o`, `u`, `x` et `X`.  Les types virgule flottante, tels que `float`, `double` et `long double`, sont spécifiés à l'aide de `a`, `A`, `e`, `E`, `f`, `g` et `G`.  Par défaut, à moins d'être modifiés par un préfixe de longueur de champ `size`, les arguments entiers sont forcés au type `int` et les arguments à virgule flottante sont forcés en `double`.  Sur les systèmes 64 bits, un `int` est une valeur 32 bits ; par conséquent, les entiers 64 bits sont tronqués quand ils sont mis en forme pour la sortie, à moins qu'un préfixe `size` `ll` ou `I64` soit utilisé.  Les types de pointeur spécifiés par `p` utilisent la longueur par défaut de la plateforme.  
  
> [!NOTE]
>  Les caractères de type `C`, `S` et `Z` et le comportement des caractères de type `c` et `s` quand ils sont utilisés avec les fonctions `printf` et `wprintf` sont des extensions Microsoft et ne sont pas compatibles ANSI.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ne prend pas en charge le type de caractère `F`.  
  
### Caractères du champ de type printf  
  
|Type de caractère|Argument|Format de sortie|  
|-----------------------|--------------|----------------------|  
|`c`|Caractère|Quand il est utilisé avec les fonctions `printf`, spécifie un caractère codé sur un octet ; quand il est utilisé avec les fonctions `wprintf`, spécifie un caractère large.|  
|`C`|Caractère|Quand il est utilisé avec les fonctions `printf`, spécifie un caractère large ; quand il est utilisé avec les fonctions `wprintf`, spécifie un caractère codé sur un octet.|  
|`d`|Entier|Entier décimal signé.|  
|`i`|Entier|Entier décimal signé.|  
|`o`|Entier|Entier octal non signé.|  
|`u`|Entier|Entier décimal non signé.|  
|`x`|Entier|Entier hexadécimal non signé ; utilise « abcdef ».|  
|`X`|Entier|Entier hexadécimal non signé ; utilise « ABCDEF ».|  
|`e`|Virgule flottante|Valeur signée se présentant sous la forme \[ – \]`d`**.**`dddd` e \[*signe*\]`dd[d]` où `d` correspond à un chiffre décimal, `dddd` à un ou plusieurs chiffres décimaux, `dd[d]` à deux ou trois chiffres décimaux selon le [format de sortie](../c-runtime-library/set-output-format.md) et la taille de l'exposant, et *signe* représente \+ ou –.|  
|`E`|Virgule flottante|Identique au format `e` sauf que l'exposant est introduit par **E** et non par **e**.|  
|`f`|Virgule flottante|Valeur signée se présentant sous la forme \[ – \] `dddd`**.**`dddd`, où `dddd` correspond à un ou plusieurs chiffres décimaux.  Le nombre de chiffres avant la virgule décimale dépend de l'ampleur du nombre, et le nombre de chiffres après que la virgule décimale dépend de la précision demandée.|  
|`g`|Virgule flottante|Les valeurs signées sont affichées au format `f` ou `e`, selon celui qui est le plus compact pour la valeur et la précision en question.  Le format `e` est utilisé uniquement quand l'exposant de la valeur est inférieure à – 4 ou supérieur ou égal à l'argument `precision`.  Les zéros de droite sont tronqués et la virgule décimale apparaît uniquement si elle est suivie d'un ou plusieurs chiffres.|  
|`G`|Virgule flottante|Identique au format `g` sauf que l'exposant est introduit par **E** et non par **e** \(selon le cas\).|  
|`a`|Virgule flottante|Valeur à virgule flottante double précision hexadécimale signée se présentant sous la forme \[−\]0x*h.hhhh* **p±**`dd`, où *h.hhhh* correspond aux chiffres hexadécimaux \(utilisant des lettres minuscules\) de la mantisse et `dd` représente un ou plusieurs chiffres pour l'exposant.  La précision indique le nombre de chiffres après la virgule.|  
|`A`|Virgule flottante|Valeur à virgule flottante double précision hexadécimale signée se présentant sous la forme \[−\]0X*h.hhhh* **P±**`dd`, où *h.hhhh* correspond aux chiffres hexadécimaux \(utilisant des lettres majuscules\) de la mantisse et `dd` représente un ou plusieurs chiffres pour l'exposant.  La précision indique le nombre de chiffres après la virgule.|  
|`n`|Pointeur désignant un entier|Nombre de caractères correctement écrits jusqu'à présent dans le flux ou la mémoire tampon.  Cette valeur est stockée dans l'entier dont l'adresse est fournie sous forme d'argument.  Consultez la section Note de sécurité plus loin dans cet article.|  
|`p`|Type de pointeur|Affiche l'argument sous forme d'adresse composée de chiffres hexadécimaux.|  
|`s`|Chaîne|Quand il est utilisé avec les fonctions `printf`, spécifie une chaîne de caractères codés sur un octet ou multioctets ; quand il est utilisé avec les fonctions `wprintf`, spécifie une chaîne de caractères larges.  Les caractères s'affichent jusqu'au premier caractère null ou jusqu'à ce que la valeur de `precision` soit atteinte.|  
|`S`|Chaîne|Quand il est utilisé avec les fonctions `printf`, spécifie une chaîne de caractères larges ; quand il est utilisé avec les fonctions `wprintf`, spécifie une chaîne de caractères codés sur un octet ou multioctets.  Les caractères s'affichent jusqu'au premier caractère null ou jusqu'à ce que la valeur de `precision` soit atteinte.|  
|`Z`|Structure `ANSI_STRING` ou `UNICODE_STRING`|Quand l'adresse d'une structure [ANSI\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff540605.aspx) ou [UNICODE\_STRING](http://msdn.microsoft.com/library/windows/hardware/ff564879.aspx) est passée comme argument, affiche la chaîne contenue dans la mémoire tampon désignée par le champ `Buffer` de la structure.  Utilisez un préfixe de modificateur de longueur `w` pour spécifier un argument `UNICODE_STRING`, par exemple, `%wZ`.  Le champ `Length` de la structure doit indiquer la longueur, en octets, de la chaîne.  Le champ `MaximumLength` de la structure doit indiquer la longueur, en octets, de la mémoire tampon.<br /><br /> En règle générale, le caractère de type `Z` est utilisé uniquement dans les fonctions de débogage de pilote qui utilisent une spécification de format, telle que `dbgPrint` et `kdPrint`.|  
  
 Si l'argument qui correspond à un spécificateur de conversion de valeurs à virgule flottante est infini, indéfini ou NAN, le tableau suivant répertorie la sortie mise en forme.  
  
|Valeur|Sortie|  
|------------|------------|  
|\+ infini|`1. #INF` *chiffres\-aléatoire*|  
|– infini|`–1.#INF` *chiffres\-aléatoires*|  
|Indéfini \(identique à une valeur NaN silencieuse\)|*chiffre* `.#IND` *chiffres\-aléatoires*|  
|NAN|*chiffre* `.#NAN` *chiffres\-aléatoires*|  
  
> [!NOTE]
>  Si le champ `Buffer` de l'argument qui correspond à `%Z` ou de l'argument qui correspond à `%s` ou `%S` est un pointeur null, « \(null\) » s'affiche.  
  
> [!NOTE]
>  Dans tous les formats exponentiels, le nombre par défaut de chiffres d'exposant affichés est de trois.  En utilisant la fonction [\_set\_output\_format](../c-runtime-library/set-output-format.md), vous pouvez définir le nombre de chiffres affichés à deux avec toutefois la possibilité de l'étendre à trois si la taille de l'exposant l'exige.  
  
> [!IMPORTANT]
>  Le format `%n` étant peu sécurisé par nature, il est désactivé par défaut.  Si `%n` est rencontré dans une chaîne de format, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../c-runtime-library/parameter-validation.md).  Pour activer la prise en charge de `%n`, consultez [\_set\_printf\_count\_output](../c-runtime-library/reference/set-printf-count-output.md).  
  
## Voir aussi  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Directives de balise](../c-runtime-library/flag-directives.md)   
 [Spécification de largeur printf](../c-runtime-library/printf-width-specification.md)   
 [Spécifications de précision](../c-runtime-library/precision-specification.md)   
 [Spécification de taille](../c-runtime-library/size-specification.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)