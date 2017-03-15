---
title: "_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cwscanf_s_l"
  - "_cwscanf_s"
  - "_cscanf_s"
  - "_cscanf_s_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "cscanf_s"
  - "cscanf_s_l"
  - "cwscanf_s"
  - "_cwscanf_s"
  - "_tcscanf_s"
  - "_cscanf_s"
  - "_cwscanf_s_l"
  - "_cscanf_s_l"
  - "cwscanf_s_l"
  - "_tcscanf_s_l"
  - "tcscanf_s"
  - "tcscanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cscanf_s (fonction)"
  - "_cscanf_s_l (fonction)"
  - "_cwscanf_s (fonction)"
  - "_cwscanf_s_l (fonction)"
  - "_tcscanf_s (fonction)"
  - "_tcscanf_s_l (fonction)"
  - "console (C++), lire dans"
  - "cscanf_s (fonction)"
  - "cscanf_s_l (fonction)"
  - "cwscanf_s (fonction)"
  - "cwscanf_s_l (fonction)"
  - "données (C++), lire à partir de la console"
  - "lire des données (C++), à partir de la console"
  - "tcscanf_s (fonction)"
  - "tcscanf_s_l (fonction)"
ms.assetid: 9ccab74d-916f-42a6-93d8-920525efdf4b
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit les données mises en forme depuis la console.  Ces versions plus sécurisées de [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md) présentent des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _cscanf_s(   
   const char *format [,  
   argument] ...   
);  
int _cscanf_s_l(   
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _cwscanf_s(   
   const wchar_t *format [,  
   argument] ...   
);  
int _cwscanf_s_l(   
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
```  
  
#### Paramètres  
 `format`  
 Chaîne de contrôle de format.  
  
 `argument`  
 Paramètres facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Le nombre de champs qui ont été correctement convertis et assignés.  La valeur de retour n'inclut pas les champs qui ont été lus mais non assignés.  La valeur de retour est `EOF` pour une tentative de lire à la fin du fichier.  Cela peut se produire lorsque l'entrée au clavier est redirigée au niveau ligne de commande du système d'exploitation.  La valeur de retour 0 signifie qu'aucun champ n'a été assigné.  
  
 Ces fonctions valident leurs paramètres.  Si `format` est un pointeur null, ces fonctions invoquent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `EOF` et `errno`est défini comme `EINVAL`.  
  
## Notes  
 La fonction `_cscanf_s` lit les données directement de la console dans les emplacements spécifiés par `argument`.  La fonction [\_getche](../../c-runtime-library/reference/getch-getwch.md) est utilisée pour lire des caractères.  Chaque paramètre optionnel doit être un pointeur vers une variable dont le type correspond à un spécificateur de type dans `format`.  Le format contrôle l'interprétation des champs d'entrée et a les mêmes formulaire et fonction que le paramètre `format` pour la fonction [](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md "scanf, _scanf_l, wscanf, _wscanf_l") .  Bien que `_cscanf_s` répercute normalement le caractère d'entrée, il ne le fait pas si le dernier appel a la valeur `_ungetch`.  
  
 Comme d'autres versions sécurisées des fonctions dans la famille`scanf`,`_cscanf_s` et `_cswscanf_s` nécessitent des arguments de taille pour les caractères de type champ `c`, `C`, `s`, `S`, et `[`.  Pour plus d'informations, consultez [Spécification de largeur scanf](../../c-runtime-library/scanf-width-specification.md).  
  
> [!NOTE]
>  Le paramètre size est de type `unsigned`, et non du type `size_t`.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcscanf_s`|`_cscanf_s`|`_cscanf_s`|`_cwscanf_s`|  
|`_tcscanf_s_l`|`_cscanf_s_l`|`_cscanf_s_l`|`_cwscanf_s_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_cscanf_s`,`_cscanf_s_l`|\<conio.h\>|  
|`_cwscanf_s`, `_cwscanf_s_l`|\<conio.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_cscanf_s.c  
// compile with: /c  
/* This program prompts for a string  
 * and uses _cscanf_s to read in the response.  
 * Then _cscanf_s returns the number of items  
 * matched, and the program displays that number.  
 */  
  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int result, n[3];  
   int i;  
  
   result = _cscanf_s( "%i %i %i", &n[0], &n[1], &n[2] );  
   _cprintf_s( "\r\nYou entered " );  
   for( i=0; i<result; i++ )  
      _cprintf_s( "%i ", n[i] );  
   _cprintf_s( "\r\n" );  
}  
```  
  
## Entrée  
  
```  
1 2 3  
```  
  
## Sortie  
  
```  
You entered 1 2 3  
```  
  
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)