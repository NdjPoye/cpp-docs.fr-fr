---
title: "Assistant Ajout d&#39;&#233;v&#233;nement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.event.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ajout d'événement (Assistant C++)"
ms.assetid: bdd2a7bb-13d5-44d7-abc9-e785ba4e05ce
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Assistant Ajout d&#39;&#233;v&#233;nement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet Assistant ajoute un événement à votre projet de contrôle ActiveX MFC.  Vous pouvez spécifier votre propre événement, personnaliser un événement stock standard ou sélectionner un événement stock dans une liste.  
  
 **Nom de l'événement**  
 Définit le nom utilisé par les clients Automation pour demander un événement de la classe.  Entrez un nom ou sélectionnez\-en un dans la liste.  
  
 **Type de l'événement**  
 Indique le type d'événement à ajouter.  Disponible uniquement si vous sélectionnez dans la liste **Nom de l'événement**.  
  
|Option|Description|  
|------------|-----------------|  
|**Boursier**|Spécifie qu'un événement stock, tel qu'un clic sur un bouton, est implémenté pour cette classe.  Les événements stock sont définis dans la Bibliothèque MFC \(Microsoft Foundation Class\).|  
|**Personnalisé**|Spécifie que vous définissez votre propre implémentation de l'événement.|  
  
 **Nom interne**  
 Définit le nom de la fonction membre qui envoie l'événement.  Disponible uniquement pour les événements personnalisés.  Ce nom est fondé sur le **Nom de l'événement**.  Vous pouvez modifier le nom interne si vous souhaitez attribuer un nom différent du **Nom de l'événement**.  
  
 **Type de paramètre**  
 Définit le type du **Nom du paramètre**.  Sélectionnez le type dans la liste.  
  
 **Nom du paramètre**  
 Définit le nom d'un paramètre à passer par l'intermédiaire de votre événement.  Une fois le nom entré, vous devez cliquer sur **Ajouter** pour l'ajouter à la liste de paramètres.  
  
 Lorsque vous cliquez sur **Ajouter**, le nom du paramètre s'affiche dans la **Liste de paramètres**.  
  
> [!NOTE]
>  Si vous fournissez un nom de paramètre et si vous cliquez ensuite sur **Terminer** avant de cliquer sur **Ajouter**, le paramètre n'est pas ajouté à l'événement.  Vous devez rechercher la méthode et insérer le paramètre manuellement. **Liste de paramètres**  
  
 **Ajouter**  
 Ajoute le paramètre que vous avez spécifié dans **Nom du paramètre**, ainsi que son type, à la **Liste de paramètres**.  Pour ajouter un paramètre à la liste, cliquez sur **Ajouter**.  
  
 **Supprimer**  
 Supprime le paramètre que vous sélectionnez de la **Liste de paramètres**.  
  
 **Liste de paramètres**  
 Affiche tous les paramètres et leurs types actuellement ajoutés pour la méthode.  Lorsque vous ajoutez des paramètres, l'Assistant met à jour la **Liste de paramètres** pour afficher chaque paramètre avec son type.  
  
## Voir aussi  
 [Ajout d'un événement](../ide/adding-an-event-visual-cpp.md)