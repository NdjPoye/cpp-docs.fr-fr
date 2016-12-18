---
title: "S&#233;rialisation des donn&#233;es dans et depuis des fichiers | Microsoft Docs"
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
  - "données (MFC)"
  - "données (MFC), sérialisation"
  - "désérialisation (C++)"
  - "données de document (C++)"
  - "documents (C++), enregistrer"
  - "documents (C++), sérialisation"
  - "enregistrer des documents"
  - "sérialisation (C++), rôle des données"
  - "sérialisation (C++), rôle de document"
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;rialisation des donn&#233;es dans et depuis des fichiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'idée de la persistance est qu'un objet doit pouvoir entrer son état actuel, indiquée par les valeurs de variables ses membres, dans un stockage permanent.  Par la suite, l'objet peut être recréé par la lecture, ou la "désérialisation", de l'état de l'objet dans le stockage permanent.  Un point clé est ici que l'objet lui\-même est chargé de lire et d'écrire son propre état.  Par conséquent, pour qu'une classe soit permanente, il doit implémenter les opérations de base de sérialisation.  
  
 L'infrastructure fournit une implémentation par défaut pour sauvegarder des documents sur le disque en réponse aux commandes Enregistrer et la Enregistrer Sous du menu Fichier et pour charger des documents depuis le disque en réponse à la commande Ouvrir.  Avec très peu de travail, vous pouvez implémenter la capacité d'un document d'écrire et de lire ses données vers et à partir d'un fichier.  La chose principale que vous devez faire est de remplacer la fonction membre [Sérialize](../Topic/CObject::Serialize.md) dans la classe de votre document.  
  
 L'Assistant d'Application MFC place une substitution squelette de la fonction membre `Serialize` de **CDocument** dans la classe de document qu'elle crée automatiquement.  Après avoir mis les variables membres de votre application en place, vous pouvez compléter votre substitution de `Serialize` avec du code qui envoie les données dans un objet « archive » connecté à un fichier.  Un objet de [CArchive](../mfc/reference/carchive-class.md) est similaire aux objets d'entrée\/sortie `cin` et `cout` de la bibliothèque iostream C\+\+.  Toutefois, `CArchive` lit et écrit le format binaire, pas le texte mis en forme.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Sérialisation](../mfc/serialization-in-mfc.md)  
  
-   [Le rôle du document dans la sérialisation](#_core_the_document.92.s_role_in_serialization)  
  
-   [Le rôle des données dans la sérialisation](#_core_the_data.92.s_role_in_serialization)  
  
-   [Ignorer le mécanisme de sérialisation](../mfc/bypassing-the-serialization-mechanism.md)  
  
##  <a name="_core_the_document.92.s_role_in_serialization"></a> Le rôle du document dans la Sérialisation  
 L'infrastructure répond automatiquement aux commandes Ouvrir, Enregistrer et Enregistrer Sous du menu Fichier en appelant la fonction membre `Serialize` du document si elle est implémentée.  Une commande de `ID_FILE_OPEN`, par exemple, appelle une fonction gestionnaire de rôles dans l'objet d'application.  Pendant ce processus, l'utilisateur visualise et répond à la boîte de dialogue ouverte de fichier et l'infrastructure obtient le nom de fichier que l'utilisateur choisit.  L'infrastructure crée une installation d'un objet de `CArchive` pour charger des données dans le document et passe l'archive à `Serialize`.  L'infrastructure a déjà ouvert le fichier.  Le code de la fonction membre `Serialize` de votre document lit les données à travers l'archive, reconstruisant les objets de données si nécessaire.  Pour plus d'informations sur la sérialisation, consultez l'article [Sérialisation](../mfc/serialization-in-mfc.md).  
  
##  <a name="_core_the_data.92.s_role_in_serialization"></a> Le rôle des données dans la sérialisation  
 En général les données de types de classe doivent se sérialiser elles\-mêmes.  Autrement dit, lorsque vous passez un objet à une archive, l'objet doit savoir comment s'écrire dans l'archive et comment se lire depuis l'archive.  MFC fournit une aide pour rendre les classes sérialisables ainsi.  Si vous concevez une classe pour définir un type de données et vous envisagez de sérialiser les données de ce type, concevez la sérialisation.  
  
## Voir aussi  
 [Utilisation de documents](../mfc/using-documents.md)