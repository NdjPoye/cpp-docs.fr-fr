---
title: "S&#233;rialisation dans MFC | Microsoft Docs"
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
  - "ignorer la sérialisation"
  - "classes de collection, sérialisation"
  - "MFC, sérialisation"
  - "sérialisation (C++), ignorer"
  - "sérialisation (C++), MFC"
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;rialisation dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit le mécanisme de sérialisation fourni dans la bibliothèque MFC \(MFC\) pour permettre aux objets de persister entre des exécutions de votre programme.  
  
 La sérialisation est le processus d'écriture ou de lecture d'un objet à partir d'un support de stockage permanent tel qu'un fichier de disque.  La sérialisation est idéale pour les situations où il est désiré de gérer l'état des données structurées \(telles que les classes ou structures C\+\+\) pendant ou après l'exécution d'un programme.  L'utilisation de la sérialisation d'objets fournis par MFC permet à cela de se passer de façon standard et cohérente, soulageant l'utilisateur de la nécessité d'effectuer des opérations de fichier à la main.  
  
 MFC fournit la prise en charge intégrée de la sérialisation de la classe `CObject`.  Par conséquent, toutes les classes dérivées `CObject` peuvent tirer parti du protocole de sérialisation de `CObject`.  
  
 L'idée de la sérialisation est qu'un objet doit pouvoir d'écrire son état actuel, généralement désigné par la valeur de ses variables membres, en stockage permanent.  Par la suite, l'objet peut être recréé par la lecture, ou la désérialisation, de l'état de l'objet dans le stockage.  La sérialisation gère tous les détails des pointeurs d'objets et des références circulaires des objets utilisés pour sérialiser un objet.  Un point clé est ici que l'objet lui\-même est chargé de lire et d'écrire son propre état.  Par conséquent, pour qu'une classe soit sérialisable, elle doit implémenter les opérations sérialisation basiques.  Comme indiqué dans le groupe d'articles sur la sérialisation, il est facile d'ajouter cette fonctionnalité dans une classe.  
  
 MFC utilise un objet de la classe `CArchive` comme intermédiaire entre l'objet à sérialiser et le support de stockage.  Cet objet est toujours associé à un objet `CFile`, à partir duquel il obtient les informations nécessaires à la sérialisation, y compris le nom de fichier et si l'opération demandée est une lecture ou une écriture.  L'objet qui effectue une opération de sérialisation peut utiliser l'objet `CArchive` indépendamment de la nature du support de stockage.  
  
 Un objet `CArchive` utilise des opérateurs surchargés d'insertion \(**\<\<**\) et d'extraction \(**\>\>**\) pour effectuer des opérations de lecture et de lecture.  Pour plus d'informations, consultez [Stockage et de CObjects via une archive](../mfc/storing-and-loading-cobjects-via-an-archive.md) dans l'article Sérialisation : Sérialiser un objet.  
  
> [!NOTE]
>  Ne confondez pas la classe `CArchive` à l'aide de classes iostream à caractère général, qui est du texte mis en forme uniquement.  La classe `CArchive` concerne les objets sérialisés au format binaire.  
  
 Si vous le souhaitez, vous pouvez ignorer la sérialisation de MFC pour créer votre propre mécanisme de stockage des données persistantes.  Vous devez remplacer les fonctions membre classe qui initie cette sérialisation à l'ordre de l'utilisateur.  Consultez la discussion dans [Note technique 22](../mfc/tn022-standard-commands-implementation.md) des commandes standard `ID_FILE_OPEN`, **ID\_FILE\_SAVE**, et **ID\_FILE\_SAVE\_AS**.  
  
 Les éléments suivants couvrent les deux tâches principales nécessaires à la sérialisation :  
  
-   [Sérialisation : définir une classe sérialisable](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Sérialisation : sérialisation d'un objet](../mfc/serialization-serializing-an-object.md)  
  
 L'article [Sérialisation : Sérialisation vs l'entrée\/sortie de base de données](../mfc/serialization-serialization-vs-database-input-output.md) indique quand la sérialisation est une technique appropriée d'entrée\/sortie dans des applications de base de données.  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)   
 [CArchive Class](../mfc/reference/carchive-class.md)   
 [CObject Class](../mfc/reference/cobject-class.md)   
 [CDocument Class](../mfc/reference/cdocument-class.md)   
 [CFile Class](../mfc/reference/cfile-class.md)