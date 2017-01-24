---
title: "Fournisseur OLE DB ATL (Assistant) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.provider.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fournisseur OLE DB ATL (Assistant)"
  - "Projets ATL, ajouter des fournisseurs OLE DB ATL"
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fournisseur OLE DB ATL (Assistant)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet Assistant crée les classes qui composent un fournisseur OLE DB.  
  
## Remarques  
 À partir de [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], le script d'inscription produit par cet Assistant inscrira ses composants COM sous **HKEY\_CURRENT\_USER** au lieu de **HKEY\_LOCAL\_MACHINE**.  Pour modifier ce comportement, définissez l'option **Inscrire le composant pour tous les utilisateurs** de l'Assistant ATL.  
  
 Le tableau suivant décrit les options de l'Assistant Fournisseur OLEDB ATL :  
  
 **Nom court**  
 Tapez le nom court du fournisseur à créer.  Les autres zones d'édition de l'Assistant se rempliront automatiquement en fonction de votre saisie.  Vous pouvez modifier les autres zones de nom si vous le souhaitez.  
  
 **CoClasse**  
 Nom de la coclasse.  Le nom du ProgID sera modifié pour correspondre à ce nom.  
  
 **Avec attributs**  
 Cette option spécifie si l'Assistant doit créer des classes de fournisseurs à l'aide d'attributs ou de déclarations de modèles.  Si vous sélectionnez cette option, l'Assistant utilise des attributs plutôt que des déclarations de modèles \(il s'agit de l'option par défaut si vous avez créé un projet avec attributs\).  Si vous désactivez cette option, l'Assistant utilise alors des déclarations de modèles plutôt que des attributs \(il s'agit de l'option par défaut si vous avez créé un projet sans attribut\).  
  
 Si vous sélectionnez cette option alors que vous avez créé un projet sans attributs, l'Assistant vous avertit que le projet sera converti en projet avec attributs et vous demande si vous souhaitez continuer.  
  
 **ProgID**  
 Le ProgID, ou identificateur programmatique, est une chaîne de texte que votre application peut utiliser plutôt qu'un GUID.  Le nom ProgID se présente sous la forme suivante : *NomProjet*.*NomCoclasse*.  
  
 **Version**  
 Numéro de version de votre fournisseur.  La valeur par défaut est 1.  
  
 **Classe DataSource**  
 Nom de la classe de sources de données, au format : C`Shortname`Source.  
  
 **Fichier .h de la source de données**  
 Fichier d'en\-tête de la classe source de données.  Vous pouvez modifier le nom de ce fichier ou sélectionner un fichier d'en\-tête existant.  
  
 **Classe Session**  
 Nom de la classe de sessions, au format : C`Shortname`Session.  
  
 **Fichier .h de session**  
 Fichier d'en\-tête de la classe session.  Vous pouvez modifier le nom de ce fichier ou sélectionner un fichier d'en\-tête existant.  
  
 **Classe Command**  
 Nom de la classe de commandes, au format : C`Shortname`Command.  
  
 **Fichier .h de command**  
 Fichier d'en\-tête de la classe command.  Ce nom ne peut pas être modifié et dépend du nom du fichier d'en\-tête rowset.  
  
 **Classe Rowset**  
 Nom de la classe rowset, au format : C`Shortname`Rowset.  
  
 **Fichier .h Rowset**  
 Fichier d'en\-tête de la classe rowset.  Vous pouvez modifier le nom de ce fichier ou sélectionner un fichier d'en\-tête existant.  
  
 **Fichier .cpp Rowset**  
 Fichier d'implémentation du fournisseur.  Vous pouvez modifier le nom de ce fichier ou sélectionner un fichier d'implémentation existant.  
  
## Voir aussi  
 [ATL OLE DB Provider](../../atl/reference/adding-an-atl-ole-db-provider.md)