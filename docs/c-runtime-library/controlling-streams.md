---
title: "Contr&#244;le des flux | Microsoft Docs"
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
  - "Controlling Streams"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "contrôler les flux"
  - "flux"
  - "flux, contrôler"
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Contr&#244;le des flux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[fopen](../c-runtime-library/reference/fopen-wfopen.md) retourne l'adresse d'un objet de type `FILE`.  Vous pouvez utiliser cette adresse comme argument `stream` pour plusieurs fonctions de la bibliothèque afin d'effectuer diverses opérations sur un fichier ouvert.  Pour un flux d'octets, toutes les entrées se déroulent comme si chaque caractère était lu en appelant [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), et la sortie se déroule comme si chaque caractère était écrit en appelant [fputc](../c-runtime-library/reference/fputc-fputwc.md).  Pour un flux large, toutes les entrées se déroulent comme si chaque caractère était lu en appelant [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), et la sortie se déroule comme si chaque caractère était écrit en appelant [fputwc](../c-runtime-library/reference/fputc-fputwc.md).  
  
 Vous pouvez fermer un fichier en appelant [fclose](../c-runtime-library/reference/fclose-fcloseall.md), après quoi l'adresse de l'objet `FILE` n'est plus valide.  
  
 Un objet `FILE` indique l'état d'un flux de données, notamment :  
  
-   Un un indicateur d'erreur retourne une valeur non nulle d'erreur par une fonction qui effectue une lecture ou renvoie une erreur.  
  
-   Un indicateur de fin de fichier retourne une valeur différente de zéro par une fonction qui répond à la fin de le fichier pendant la lecture.  
  
-   Un indicateur d'emplacement de fichier spécifie l'octet suivant dans le flux de données pour lire ou écrire, si le fichier peut prendre en charge le positionnement des requêtes.  
  
-   [état de flux de données](../c-runtime-library/stream-states.md) spécifie si le flux de données accepte des lectures et\/ou des écritures et si le flux est limité, byte\-oriented, ou wide\-oriented.  
  
-   Une état de conversion se souvient de l'état de chaque caractères multioctets généré ou en partie assemblé, ainsi que toute condition du décalage de la séquence d'octets du fichier\).  
  
-   Une mémoire tampon de fichiers spécifie l'adresse et la taille d'un objet, que des fonctions de la bibliothèque peuvent utiliser pour améliorer les performances des opérations de lecture et d'écriture de flux de données.  
  
 Ne modifiez pas de valeur stockée dans un objet `FILE` ou dans une mémoire tampon de fichier que vous spécifiez pour une utilisation avec cet objet.  Vous ne pouvez pas copier un objet `FILE` et utiliser ailleurs l'adresse d'envoi en tant qu'argument `stream` dans une fonction de le bibliothèque.  
  
## Voir aussi  
 [Fichiers et flux](../c-runtime-library/files-and-streams.md)