---
title: "Deux mani&#232;res de cr&#233;er un objet CArchive | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive (classe), fermer des objets CArchive"
  - "CArchive (classe), constructeur"
  - "objets CArchive"
  - "objets CArchive, fermer"
  - "stockage des données (C++), CArchive (classe)"
  - "E/S (MFC), créer des objets CArchive"
  - "sérialisation (C++), CArchive (classe)"
  - "stockage (C++), CArchive (classe)"
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Deux mani&#232;res de cr&#233;er un objet CArchive
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe deux manières de créer un objet `CArchive`:  
  
-   [Création implicite d'un objet CArchive via le framework](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [Création explicite d'un objet CArchive](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> Création implicite d'un objet CArchive via le framework  
 La méthode la plus courante, et la plus simple, consiste à permettre au framework de créer un objet `CArchive` pour votre document au nom des commandes de sauvegarde, sauvegarde, et ouverture du menu Fichier.  
  
 Voici ce que l'infrastructure effectue lorsque l'utilisateur de votre application émet la commande enregistrer sous dans le menu Fichier :  
  
1.  Affiche la boîte de dialogue **Enregistrer sous** et obtient le nom de fichier de l'utilisateur.  
  
2.  Ouvre le fichier nommé par l'utilisateur en tant qu'objet `CFile`.  
  
3.  Crée un objet `CArchive` qui pointe vers cet `CFile` objet.  Lors de la création de l'objet `CArchive`, le framework définit le mode sur « stockage » \(écriture, sérialisation\), par opposition à « chargement » \(lecture, désérialisation\).  
  
4.  Appelle la fonction `Serialize` définie dans votre classe dérivée de **CDocument**, et lui transmet une référence à l'objet `CArchive`.  
  
 La fonction `Serialize` de votre document écrit les données dans l'objet `CArchive`, comme expliqué.  Lors du retour de la fonction `Serialize`, le framework détruit l'objet `CArchive` puis l'objet `CFile`.  
  
 Par conséquent, si vous laissez le framework créer l'objet `CArchive` pour votre document, il vous suffit d'implémentation de la fonction `Serialize` du document qui écrit et la lit vers et depuis l'archive.  Vous devez également implémenter `Serialize` pour tous les objets dérivés de`CObject` que la fonction `Serialize` du document sérialise ensuite directement ou indirectement.  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a> Création explicite d'un objet CArchive  
 Outre la sérialisation un document via le framework, il existe d'autres occasions dans lesquelles vous aurez besoin d'un objet `CArchive`.  Par exemple, vous pouvez sérialiser des données vers le presse\-papiers, représenté par un objet `CSharedFile`.  Ou, vous pouvez utiliser une interface utilisateur pour stocker un fichier qui est différent de celui proposé par l'infrastructure.  Dans ce cas, vous pouvez explicitement créer un objet `CArchive`.  Vous faites cela de la même façon que le framework, à l'aide de la procédure suivante.  
  
#### Pour créer explicitement un objet de CArchive  
  
1.  Construisez un objet `CFile` ou un objet dérivé de `CFile`.  
  
2.  Passez l'objet `CFile` au constructeur de `CArchive`, comme le montre l'exemple suivant :  
  
     [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/CPP/two-ways-to-create-a-carchive-object_1.cpp)]  
  
     Le deuxième argument du constructeur `CArchive` est une valeur énumérée de la propriété qui spécifie si l'archive sera utilisée pour enregistrer ou charger des données à partir du fichier.  La fonction `Serialize` d'un objet vérifie cet état en appelant la fonction `IsStoring` pour l'objet archive.  
  
 Lorsque vous avez terminé l'enregistrement ou le chargement des données à partir de `CArchive` objet, fermez\-le.  Bien que les objets `CArchive` \(et `CFile`\) fermeront automatiquement l'archive \(et le fichier\), il est recommandé de le faire explicitement car cela permet la récupération des erreurs.  Pour plus d'informations sur la gestion des erreurs, consultez l'article [Exceptions : Intercepter et supprimer des exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
#### Pour fermer l'objet CArchive  
  
1.  L'exemple suivant illustre comment fermer l'objet `CArchive` :  
  
     [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/CPP/two-ways-to-create-a-carchive-object_2.cpp)]  
  
## Voir aussi  
 [Sérialisation : sérialisation d'un objet](../mfc/serialization-serializing-an-object.md)