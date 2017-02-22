---
title: "ungetc, ungetwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ungetwc"
  - "ungetc"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ungettc"
  - "ungetwc"
  - "ungetc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ungettc (fonction)"
  - "caractères, push vers le flux"
  - "ungetc (fonction)"
  - "ungettc (fonction)"
  - "ungetwc (fonction)"
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ungetc, ungetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Repousse un caractère vers le flux.  
  
## Syntaxe  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à renvoyer.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 En cas de réussite, chacune de ces fonctions retourne l'argument `c`de caractère*.* Si `c` ne peut pas être refoulé ou si aucun caractère n'a été lu, le flux d'entrée est inchangé et `ungetc` retourne `EOF`; `ungetwc` retourne `WEOF`.  Si `stream` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre,  `EOF` ou `WEOF` est retourné et `errno` est affecté à la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes d'erreur et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `ungetc` renvoie le caractère `c` vers `stream` et désactive l'indicateur de fin de fichier.  Le flux doit être ouvert pour la lecture.  Une opération de lecture à venir sur `stream` commence avec `c`*.* Une tentative de pousser `EOF` sur le flux en utilisant `ungetc` est ignorée.  
  
 Les caractères placés sur le flux par `ungetc` peuvent être effacés si `fflush`, `fseek`, `fsetpos`, ou `rewind` est appelé avant que le caractère soit lu depuis le flux.  L'indicateur de la position du fichier aura la valeur qu'il avait avant que les caractères ont été refoulés.  Le stockage externe correspondant au flux reste inchangé.  Dans un appel réussi `ungetc` à un flux de texte, l'indicateur de position de fichier n'est pas spécifié jusqu'à ce que tous les caractères refoulés soient lus ou ignorés.  À chaque appel réussi `ungetc` à un flux binaire, l'indicateur de position de fichier est décrémenté ; si sa valeur était 0 avant un appel, la valeur n'est pas définie après l'appel.  
  
 Les résultats sont imprévisibles si `ungetc` est appelé deux fois sans opération de lecture ou de positionnement de fichier entre les deux appels.  Après un appel à `fscanf`, un appel à `ungetc` peut échouer à moins qu'une autre opération de lecture \(comme `getc`\) a été effectuée.  Ceci car `fscanf` lui\-même appelle `ungetc`.  
  
 `ungetwc` est une version à caractère élargi de `ungetc`.  Toutefois, à chaque appel réussi `ungetwc` à un texte ou un flux binaire, la valeur de l'indicateur de position de fichier n'est pas spécifiée jusqu'à ce que tous les caractères refoulés soient lus ou ignorés.  
  
 Ces fonctions sont des données sécurisées du point de vue du thread et sensibles au lock pendant l'exécution.  Pour une version non verrouillante, consultez [\_ungetc\_nolock, \_ungetwc\_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`ungetc`|\<stdio.h\>|  
|`ungetwc`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
  **Nombre `521a` \= 521**  
**Caractère suivant du flux \= « a »**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)