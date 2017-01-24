---
title: "Lecture et &#233;criture de fichiers | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFile (classe), objets"
  - "CFile (classe), lire et écrire des objets CFile"
  - "exemples (MFC), lire des fichiers"
  - "exemples (MFC), écrire dans les fichiers"
  - "fichiers (C++), lire"
  - "fichiers (C++), écrire dans"
  - "MFC (C++), opérations sur les fichiers"
  - "lire des fichiers"
  - "écrire dans les fichiers (C++)"
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Lecture et &#233;criture de fichiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous avez utilisé les fonctions de gestion des fichiers de bibliothèque run\-time C, la lecture et l'écriture des opérations MFC vous apparaîtront familières.  Cet article explique comment lire et écrire directement à un objet `CFile`.  Vous pouvez également effectuer les E\/S de fichier mis en mémoire tampon avec la classe [CArchive](../mfc/reference/carchive-class.md).  
  
#### Pour lire et écrire dans le fichier.  
  
1.  Utilisez les fonctions membres **Lecture** et **Écriture** pour lire et écrire des données dans le fichier.  
  
     ou  
  
2.  La fonction membre `Seek` est également disponible pour accéder à un décalage spécifique dans le fichier.  
  
 **Lecture** prend un pointeur vers une mémoire tampon et le nombre d'octets à lire et retourne le nombre réel d'octets qui ont été lus.  Si le nombre d'octets requis ne peut pas être lus parce que la fin du fichier \(EOF\) est atteinte, le nombre réel d'octets lus est retourné.  Si une erreur de lecture se produit, une exception est levée.  **Écriture** est similaire à **Lecture**, mais le nombre d'octets écrits n'est pas retourné.  Si une erreur d'écriture se produit, notamment ne pas écrire tous les octets spécifiés, une exception est levée.  Si vous avez un objet valide `CFile`, vous pouvez lire depuis celui\-ci ou de écrire dessus comme le montre l'exemple suivant :  
  
 [!code-cpp[NVC_MFCFiles#2](../mfc/codesnippet/CPP/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  Vous devez généralementmener des opérations d'entrée\/sortie dans un bloc de gestion des exceptions **try**\/**catch**.  Pour plus d'informations, consultez [Gestion des exceptions \(MFC\)](../mfc/exception-handling-in-mfc.md).  
  
## Voir aussi  
 [Fichiers](../mfc/files-in-mfc.md)