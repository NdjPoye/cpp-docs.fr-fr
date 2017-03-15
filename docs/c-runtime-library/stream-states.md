---
title: "&#201;tats de flux | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flux, états"
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# &#201;tats de flux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les états valides, et les transitions d'état, pour un flux de données sont affichés dans l'illustration suivante.  
  
 ![Flux de données](../c-runtime-library/media/stream.png "stream")  
  
 Chacun des cercles indique un état stable.  Chaque ligne indique une transition qui peut se produire suite à un appel de fonction qui traite le flux de données.  Cinq groupes de fonctions peuvent provoquer des transitions d'état.  
  
 Les fonctions dans les trois premiers groupes sont déclarées dans \<stdio.h :\>  
  
-   Les fonctions de lecture d'octet — [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc](../c-runtime-library/reference/getc-getwc.md), [getchar](../c-runtime-library/reference/getc-getwc.md), [obtient](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), et [ungetc](../c-runtime-library/reference/ungetc-ungetwc.md)  
  
-   Les fonctions d'écriture d'octet — [fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fputs](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [met](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), et [vprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
  
-   Les fonctions de position — [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md), et [rembobinage](../c-runtime-library/reference/rewind.md)  
  
 Les fonctions des deux groupes restants sont déclarées dans \<wchar.h :\>  
  
-   Les fonctions de lecture large — [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md), et, [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)  
  
-   Les fonctions d'écriture large — [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md), et, [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
  
 Le diagramme d'état indique que vous devez appeler l'une des fonctions de position entre la plupart des opérations de lecture et d'écriture :  
  
-   Vous ne pouvez pas appeler une fonction de lecture si la dernière opération sur le flux est une écriture.  
  
-   Vous ne pouvez pas appeler une fonction d'écriture si la dernière opération sur le flux est une lecture, sauf si cette opération de lecture définit l'indicateur de fin de fichier.  
  
 Enfin, le diagramme d'état indique qu'une opération de position ne diminue jamais le nombre d'appels de fonction valides qui peuvent suivre.  
  
## Voir aussi  
 [Fichiers et flux](../c-runtime-library/files-and-streams.md)