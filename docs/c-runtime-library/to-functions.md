---
title: "to, fonctions | Microsoft Docs"
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
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "To"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "casse, convertir"
  - "caractères, convertir"
  - "minuscules, convertir des chaînes"
  - "conversion de chaînes, casse"
  - "conversion de chaînes, en caractères différents"
  - "en fonctions"
  - "majuscules, convertir des chaînes"
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# to, fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chacune des fonctions **to** et leur macro associée, si elle existe, converti un unique caractère en un autre.  
  
|||  
|-|-|  
|[\_\_toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper, \_toupper, towupper](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|  
|[tolower, \_tolower, towlower](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||  
  
## Notes  
 Les fonctions**to** et les conversions macro sont comme suit.  
  
|Routine|Macro|Description|  
|-------------|-----------|-----------------|  
|`__toascii`|`__toascii`|Convertit `c`en caractère ASCII|  
|`tolower`|`tolower`|Convertit `c` en minuscules si nécessaire|  
|`_tolower`|`_tolower`|Convertit `c` en minuscules|  
|`towlower`|None|Convertit `c` à la lettre minuscule de caractères larges correspondante|  
|`toupper`|`toupper`|Convertit `c` en majuscules si nécessaire|  
|`_toupper`|`_toupper`|Convertit `c` en majuscules|  
|`towupper`|None|Convertit c en la lettre majuscule en caractères larges correspondante|  
  
 Pour utiliser les versions de la fonction des routines **to** qui sont également définies comme macros, soit supprimez les définitions de macros avec d`#undef` ou n'incluez pas CTYPE.H.  Si vous utilisez l'option de le compilateur  \/Za, le compilateur utilise la version de la fonction de `toupper` ou de`tolower`.  Les déclarations des fonctions `toupper` et `tolower` sont dans. STDLIB.H.  
  
 La routine `__toascii` définit toutes les valeurs sauf les 7 bits de poids faibles de`c` à 0, de sorte que la valeur convertie représente un caractère du jeu de caractères ASCII.  Si `c` représente déjà un caractère ASCII, `c` reste inchangé.  
  
 Les routines `tolower` et `toupper` :  
  
-   Sont dépendent de la catégorie`LC_CTYPE` des paramètres régionaux actuels \(`tolower` appelle `isupper` et `toupper` appelle `islower`\).  
  
-   Convertissez `c` si `c` représente une lettre convertible de  la casse appropriée dans les paramètres régionaux actuels et la casse opposée existe pour les paramètres régionaux.  Sinon, `c` reste inchangé.  
  
 Les routines `_tolower` et `_toupper` :  
  
-   Sont des versions indépendantes des paramètres régionaux et beaucoup plus rapides de `tolower` et de **toupper.**  
  
-   Peut être utilisé uniquement lorsque **isascii\(**`c`**\)** et **isupper\(**`c`**\)** ou **islower\(**`c`**\)**, respectivement, est différent de zéro.  
  
-   Ont des résultats indéfinis si `c` n'est pas une lettre ASCII de la casse appropriée pour la conversion.  
  
 Les fonctions `towlower` et `towupper` retourne une copie convertie de`c` si et seulement si les deux conditions suivantes sont différentes de zéro.  Sinon, `c` reste inchangé.  
  
-   `c` est un caractère large de la casse appropriée \(autrement dit, pour les `iswupper` ou **iswlower,** respectivement, est différent de zéro\).  
  
-   Il existe un caractère large correspondant du cas cible \(autrement dit, pour les `iswlower` ou **iswupper,** respectivement, est différent de zéro\).  
  
## Exemple  
  
```  
// crt_toupper.c  
/* This program uses toupper and tolower to  
 * analyze all characters between 0x0 and 0x7F. It also  
 * applies _toupper and _tolower to any code in this  
 * range for which these functions make sense.  
 */  
  
#include <ctype.h>  
#include <string.h>  
  
char msg[] = "Some of THESE letters are Capitals.";  
char *p;  
  
int main( void )  
{  
   printf( "%s\n", msg );  
  
   /* Reverse case of message. */  
   for( p = msg; p < msg + strlen( msg ); p++ )  
   {  
      if( islower( *p ) )  
         putchar( _toupper( *p ) );  
      else if( isupper( *p ) )  
         putchar( _tolower( *p ) );  
      else  
         putchar( *p );  
   }  
}  
```  
  
  **Certaines de CES sont des lettres majuscules.**  
**cERTAINES DE ces LETTRES SONT des mAJUSCULES.**   
## Voir aussi  
 [Conversion de données](../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../c-runtime-library/locale.md)   
 [is, isw, routines](../c-runtime-library/is-isw-routines.md)