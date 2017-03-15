---
title: "Ajouter une ressource, bo&#238;te de dialogue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.insertresource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ressources (Visual Studio), ajout"
  - "Ajouter une ressource (boîte de dialogue)"
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Ajouter une ressource, bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette boîte de dialogue pour ajouter des ressources à un projet d’application de bureau Windows C\+\+.  
  
> [!NOTE]
>  Ces informations ne s’appliquent pas aux ressources dans les applications du Windows Store. Pour plus d’informations, consultez [Définition des ressources d’une application](http://msdn.microsoft.com/fr-fr/476ea844-632c-4467-9ce3-966be1350dd4).  
  
 **Type de ressource**  
 Spécifie le type de ressource que vous voulez créer.  
  
 Vous pouvez développer les catégories de ressources curseur et boîte de dialogue pour afficher des ressources supplémentaires. Ces ressources sont trouvent dans ...\\Microsoft Visual Studio `version`\\VC\\VCResourceTemplates\\\<LCID\>\\mfc.rct. Si vous ajoutez des fichiers .rct, vous devez les placer dans ce répertoire ou vous devez spécifier un [chemin include](../windows/how-to-specify-include-directories-for-resources.md) pour eux. Les ressources de ces fichiers apparaissent alors au deuxième niveau en dessous de la catégorie appropriée. Il n’existe pas de limite prédéfinie au nombre de fichiers .rct que vous pouvez ajouter.  
  
 Les ressources affichées au niveau le plus élevé du contrôle d’arborescence sont les ressources par défaut fournies par Visual Studio.  
  
 **Nouveau**  
 Crée une ressource basée sur le type que vous avez sélectionné dans la zone **Type de ressource**. La ressource s’ouvre dans l’éditeur approprié. Par exemple, si vous créez une ressource de boîte de dialogue, elle s’ouvre dans l’[éditeur de boîte de dialogue](../mfc/dialog-editor.md).  
  
 **Import**  
 Ouvre la boîte de dialogue **Importer**, où vous pouvez accéder à une ressource que vous voulez importer dans votre projet actuel. Vous pouvez importer un bitmap, une icône, un curseur, un fichier de ressources HTML, un fichier de ressources audio \(.WAV\) ou un fichier de ressources personnalisées.  
  
 **Personnalisé**  
 Ouvre la [boîte de dialogue Nouvelle ressource personnalisée](../windows/new-custom-resource-dialog-box.md), où vous pouvez créer une ressource personnalisée. Les ressources personnalisées peuvent être modifiées seulement dans l’éditeur binaire.  
  
## Spécifications  
 Aucun  
  
## Voir aussi  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)