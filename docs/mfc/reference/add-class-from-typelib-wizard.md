---
title: "Assistant Ajout de classes d&#39;une Typelib | Microsoft Docs"
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
  - "vc.codewiz.class.typelib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ajout de classes d'une TypeLib (Assistant C++)"
  - "interfaces COM, ajouter des classes"
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Ajout de classes d&#39;une Typelib
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant pour ajouter une classe MFC à partir d'une bibliothèque de types disponible.  L'Assistant crée une classe pour chaque interface que vous avez ajoutée à partir de la bibliothèque de types sélectionnée.  
  
 **Ajouter une classe à partir de**  
 Spécifie l'emplacement de la bibliothèque de types à partir de laquelle la classe est créée.  
  
|Option|Description|  
|------------|-----------------|  
|**Registre**|La bibliothèque de types est inscrite dans le système.  Les bibliothèques de types inscrites sont énumérées dans l'option **Bibliothèques de types disponibles**.|  
|**Fichier**|La bibliothèque de types n'est pas nécessairement inscrite dans le système, mais est contenue dans un fichier.  Vous devez indiquer l'emplacement du fichier dans l'option **Emplacement**.|  
  
 **Bibliothèques de types disponibles**  
 Énumère les bibliothèques de types actuellement inscrites sur le système.  Sélectionnez une bibliothèque de types dans cette liste pour afficher ses interfaces dans la liste **Interfaces**.  
  
 Pour plus d'informations sur l'inscription de bibliothèques de types, consultez « Inside Distributed COM: Type Libraries and Language Integration » dans MSDN Library.  
  
 **Emplacement**  
 Spécifie l'emplacement de la bibliothèque de types.  Si vous cliquez sur **Fichier** sous **Ajouter une classe à partir de**, vous pouvez indiquer l'emplacement du fichier contenant la bibliothèque de types.  Pour accéder à l'emplacement du fichier, cliquez sur le bouton de sélection.  
  
 **Interfaces**  
 Énumère les interfaces contenues dans la bibliothèque de types actuellement sélectionnée dans la liste **Bibliothèques de types disponibles**.  
  
|Bouton de transfert|Description|  
|-------------------------|-----------------|  
|**\>**|Ajoute l'interface actuellement sélectionnée dans la liste **Interfaces**.  Estompé si aucune interface n'est sélectionnée.|  
|**\>\>**|Ajoute toutes les interfaces contenues dans la bibliothèque de types actuellement sélectionnée dans la liste **Bibliothèques de types disponibles**.|  
|**\<**|Supprime la classe actuellement sélectionnée dans la liste **Classes générées**.  Estompé si aucune classe n'est actuellement sélectionnée dans la liste **Classes générées**.|  
|**\<\<**|Supprime toutes les classes de la liste **Classes générées**.  Estompé si la liste **Classes générées** est vide.|  
  
 **Classes générées**  
 Spécifie les noms de classe qui seront générés à partir des interfaces ajoutées à l'aide du bouton **\>\>** ou du bouton **\>\>** .  Vous pouvez cliquer sur cette zone pour sélectionner une classe, puis utiliser les touches Haut ou Bas pour faire défiler la liste, afin d'afficher chaque nom de classe dans la zone `Class` et chaque nom de fichier dans la zone **Fichier** que l'Assistant doit générer lorsque vous cliquez sur **Terminer**.  Vous ne pouvez sélectionner qu'une seule classe à la fois dans cette zone.  
  
 Pour supprimer une classe, sélectionnez\-la dans la liste et cliquez sur **\<\<**.  Vous n'avez pas besoin de sélectionner une classe dans la section classes générées pour supprimer toutes les classes; en cliquant sur : **\<\<**, vous supprimez toutes les classes dans la zone **Classes générées** .  
  
 `Class`  
 Spécifie le nom de la classe sélectionnée dans la zone **Classes générées** que l'Assistant doit ajouter lorsque vous cliquez sur **Terminer**.  Vous pouvez modifier ce nom dans la zone `Class`.  
  
 **Fichier**  
 Définit le nom du fichier d'en\-tête de la nouvelle classe.  Par défaut, ce nom est fondé sur le nom que vous avez entré dans la zone **Classes générées**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous sélectionnez un fichier existant, l'Assistant ne l'enregistrera pas à l'emplacement choisi tant que vous n'aurez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
## Voir aussi  
 [Classe MFC à partir d'une bibliothèque de types](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)   
 [Clients Automation : utilisation des bibliothèques de types](../../mfc/automation-clients-using-type-libraries.md)