---
title: "UNIX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unix"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compatibilité avec POSIX"
  - "noms de fichiers POSIX"
  - "UNIX"
  - "UNIX, compatibilité"
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# UNIX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous envisagez de porter vos programmes vers UNIX, suivez les instructions suivantes :  
  
-   Ne supprimez pas les fichiers d'en\-tête dans le sous\-répertoire de SYS.  Vous pouvez placer les fichiers d'en\-tête de SYS ailleurs à condition que vous ne projetez pas de transporter les programmes pour UNIX.  
  
-   Utilisez le délimiteur de chemin UNIX\- compatible dans les routines qui acceptent des chaînes utilisant les chemins d'accès et de fichier comme arguments.  UNIX prend uniquement en charge la barre oblique \(\/\) à cet effet, tandis que les systèmes d'exploitation Win32 prennent en charge la barre oblique inverse \(\\\) et la barre oblique \(\/\).  Par ailleurs, cette documentation utilise des barres obliques UNIX\- compatibles comme séparateurs de chemin d'accès dans les instructions `#include`, par exemple. \(Toutefois, l'environnement de commande du système d'exploitation Windows, CMD.EXE, ne prend pas en charge la barre oblique dans les commandes entrées via l'invite de commandes.\)  
  
-   Utilisez des chemins d'accès et des noms de fichiers qui fonctionnent correctement avec UNIX, respectant la casse.  Le système de fichiers de la table d'allocation des fichiers \(FAT\) dans les systèmes d'exploitation Win32 ne tient pas compte la casse ; le système de fichiers NTFS empêche la casse pour obtenir la liste des répertoires mais ignore la casse dans les recherches de fichiers et d'autres opérations du système.  
  
    > [!NOTE]
    >  Dans cette version de Visual C\+\+, les informations de compatibilité pour UNIX ont été supprimées des descriptions de fonction.  
  
## Voir aussi  
 [Compatibilité](../c-runtime-library/compatibility.md)