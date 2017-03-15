---
title: "Recommandations relatives &#224; la gestion des entr&#233;es/sorties | Microsoft Docs"
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
  - "options d'E/S basées sur les fichiers"
  - "E/S (C++)"
  - "E/S (C++), options basées sur les fichiers"
  - "E/S (C++), options"
  - "E/S (MFC), à propos d'E/S"
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Recommandations relatives &#224; la gestion des entr&#233;es/sorties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Que vous utilisiez les E\/S basées sur des fichiers ou non dépend de la façon dont vous répondez aux questions de l'arbre de décision suivant :  
  
 **Les données primaire dans votre application résident\-elles dans un fichier de disque ?**  
  
-   Oui, les données primaires résident dans un fichier de disque :  
  
     **Est\-ce que l'application lit l'ensemble du fichier en mémoire sur le fichier et écrit l'ensemble du fichier sur le disque dans la sauvegarde de fichier ?**  
  
    -   Oui: C'est le cas par défaut des documents de MFC.  Utilisez la sérialisation **CDocument**.  
  
    -   Non: C'est généralement le cas pour les mises à jour basées sur les transactions du fichier.  Vous mettez à jour le dossier pour chaque transaction et vous n'avez pas besoin de la sérialisation de **CDocument**.  
  
-   Non, les données primaires ne résident pas dans un fichier de disque:  
  
     **Les données résident\-elles dans une source de données ODBC ?**  
  
    -   Oui, les données résident dans une source de données ODBC:  
  
         Utilisez la prise en charge des bases de données MFC.  L'implémentation MFC standard pour ce cas inclut un objet de **CDocument** qui stocke un objet de `CDatabase`, comme décrit dans l'article [Quel est le modèle de programmation de base de données MFC ?](../data/what-is-the-mfc-database-programming-model-q.md).  L'application peut également lire et écrire un fichier auxiliaire — l'objectif de l'Application « une option de vue de base de données et une option de prise en charge du fichier ».  Dans ce cas, vous devriez utiliser la sérialisation pour le fichier auxiliaire.  
  
    -   Non, les données ne se trouvent pas dans une source de données ODBC.  
  
         Exemples pour ce cas: les données résident dans un SGBD non\-ODBC ; les données sont lues via un autre mécanisme, par exemple OLE ou DDE.  
  
         Dans ce cas, vous n'utiliserez pas la sérialisation, et votre application n'aura pas les menus Ouvrir et Sauvegarder.  Vous pouvez vouloir utiliser un **CDocument** comme une base d'origine, juste comme une application ODBC MFC qui utilise le document pour stocker des objets `CRecordset`.  Mais vous n'utiliserez pas le fichier par défaut de l'infrastructure Ouvrir\/Sauvegarder de sérialisation du document.  
  
 Pour prendre en charge l'ouverture, la sauvegarde et la sauvegarde sous en tant que commandes du menu Fichier, l'infrastructure fournit la sérialisation du document.  La sérialisation lit et écrit des données, y compris les objets issus de la classe `CObject`, à la mémoire permanente, normalement un fichier de disque.  La sérialisation est facile à utiliser et sert plusieurs de vos besoins, mais elle peut être inappropriée dans de nombreuses applications d'accès aux données.  Les applications d'accès aux données mette typiquement à jour leurs données pour chaque transaction.  Ils mettent à jour les enregistrements concernés par la transaction au lieu de lire et écrire un fichier de données d'un seul coup.  
  
 Pour plus d'informations sur la sérialisation, consultez [Serialization](../mfc/serialization-in-mfc.md).  
  
## Voir aussi  
 [Sérialisation : sérialisation et entrées\/sorties de base de données](../mfc/serialization-serialization-vs-database-input-output.md)