---
title: "Ignorer le m&#233;canisme de s&#233;rialisation | Microsoft Docs"
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
  - "objets archive (C++)"
  - "archives (C++)"
  - "archives (C++), sérialisation"
  - "ignorer la sérialisation"
  - "sérialisation (C++), ignorer"
  - "sérialisation (C++), substituer"
  - "sérialisation (C++), rôle de l'infrastructure"
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ignorer le m&#233;canisme de s&#233;rialisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme vous l'avez vu, l'infrastructure fournit une méthode par défaut pour lire et écrire des données dans et à partir de fichiers.  La sérialisation par le biais d'un objet archive est adaptée aux besoins d'un grand nombre d'applications.  Une application lit un fichier entièrement en mémoire, permet à l'utilisateur de mettre le fichier à jour, puis entre la version mise à jour sur le disque à nouveau.  
  
 Toutefois, certaines applications traitent les données très différemment, et pour ces applications, la sérialisation par le biais d'une archive n'est pas appropriée.  Les exemples incluent des outils de base de données, les programmes qui modifient uniquement les parties de fichiers volumineux, les programmes qui écrivent des fichiers texte, et les programmes qui partagent des fichiers de données.  
  
 Dans ces cas, vous pouvez remplacer la fonction [Serialize](../Topic/CObject::Serialize.md) d'une manière différente pour mener les actions de fichier via un objet [CFile](../mfc/reference/cfile-class.md) plutôt qu'un objet [CArchive](../mfc/reference/carchive-class.md).  
  
 Vous pouvez utiliser les méthodes **Open**, **Read**, **Write**, **Close**,  et`Seek` de la classe `CFile` pour ouvrir un fichier, déplacer le pointeur de fichier \(accès\) à un point spécifique dans le fichier, lire un enregistrement \(un nombre spécifié d'octets\) à ce point, laisser l'utilisateur mettre à jour l'enregistrement, puis revenir au même point de nouveau et entrer l'enregistrement dans le fichier.  L'infrastructure ouvre le fichier à votre place, et vous pouvez utiliser la méthode `GetFile` de la classe `CArchive` pour obtenir un pointeur vers l'objet `CFile`.  Pour une utilisation encore plus complexe et flexible, vous pouvez remplacer les méthodes [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) et [OnSaveDocument](../Topic/CDocument::OnSaveDocument.md) de la classe `CWinApp`.  Pour plus d'informations, consultez la classe [CFile](../mfc/reference/cfile-class.md) dans *le guide de MFC*.  
  
 Dans ce scénario, la substitution de `Serialize` n'a aucun effet, sauf si, par exemple, vous souhaitez l'utiliser en lecture et écrire un en\-tête de fichier pour le maintenir à jour lorsque le document se ferme.  
  
## Voir aussi  
 [Utilisation de documents](../mfc/using-documents.md)