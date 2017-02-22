---
title: "Assistant Ajout d&#39;une classe &#224; partir d&#39;un contr&#244;le ActiveX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.axcontrol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Contrôle ActiveX"
  - "Ajout d'une classe à partir d'un contrôle ActiveX (Assistant C++)"
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Assistant Ajout d&#39;une classe &#224; partir d&#39;un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant pour ajouter une classe MFC à partir d'un contrôle ActiveX disponible.  L'Assistant crée une classe pour chaque interface que vous ajoutez à partir du contrôle ActiveX sélectionné.  
  
 **Ajouter une classe à partir de**  
 Spécifie l'emplacement de la bibliothèque de types à partir de laquelle la classe est créée.  
  
|Option|Description|  
|------------|-----------------|  
|**Registre**|La bibliothèque de types est inscrite dans le système.  Les bibliothèques de types inscrites sont énumérées dans l'option **Contrôles ActiveX disponibles**.|  
|**Fichier**|La bibliothèque de types n'est pas nécessairement inscrite dans le système, mais est contenue dans un fichier.  Vous devez indiquer l'emplacement du fichier dans l'option **Emplacement**.|  
  
 **Contrôles ActiveX disponibles**  
 Spécifie les contrôles ActiveX actuellement inscrits dans le système.  Sélectionne un contrôle ActiveX dans cette liste pour afficher ses interfaces dans la liste **Interfaces**.  Pour plus d'informations sur l'inscription des contrôles ActiveX, consultez [Contrôles ActiveX MFC : distribution de contrôles ActiveX](../mfc/mfc-activex-controls-distributing-activex-controls.md).  
  
 Si vous cliquez sur **Fichier** sous **Ajouter une classe à partir de**, cette case à cocher n'est pas disponible pour la modification.  
  
 **Emplacement**  
 Spécifie l'emplacement du contrôle ActiveX.  Si vous cliquez sur **Fichier** sous **Ajouter une classe à partir de**, vous pouvez indiquer l'emplacement du fichier contenant la bibliothèque de types.  Pour accéder à l'emplacement du fichier, cliquez sur le bouton de sélection.  
  
 Si vous cliquez sur **Registre** sous **Ajouter une classe à partir de**, cette case à cocher n'est pas disponible pour la modification.  
  
 **Interfaces**  
 Spécifie les interfaces du contrôle ActiveX sélectionné dans **Contrôles ActiveX disponibles** ou de la bibliothèque de types du fichier spécifié dans **Emplacement**.  
  
|Bouton de transfert|Description|  
|-------------------------|-----------------|  
|**\>**|Ajoute l'interface actuellement sélectionnée dans la liste **Interfaces**.  Indisponible si aucune interface n'est sélectionnée.|  
|**\>\>**|Ajoute toutes les interfaces dans le contrôle ActiveX sélectionné dans **Contrôles ActiveX disponibles** ou dans la bibliothèque de types du fichier spécifié dans **Emplacement**.|  
|**\<**|Supprime la classe actuellement sélectionnée dans la liste **Classes générées**.  Indisponible si aucune classe n'est sélectionnée dans la liste **Classes générées**.|  
|**\<\<**|Supprime toutes les classes de la liste **Classes générées**.  Indisponible si la liste **Classes générées** est vide.|  
  
 **Classes générées**  
 Spécifie les noms de classe qui seront générés à partir des interfaces ajoutées à l'aide du bouton **\>** ou **\>\>**.  Vous pouvez activer cette case à cocher pour sélectionner une classe, puis recourir aux touches Haut ou Bas pour parcourir la liste en affichant chaque nom de classe dans la zone `Class` et le nom du fichier dans la zone **fichier.h** que l'Assistant génère lorsque vous cliquez sur le bouton **Terminer**.  Vous ne pouvez sélectionner qu'une seule classe à la fois dans cette zone.  
  
 Pour supprimer une classe, sélectionnez\-la dans la liste et cliquez sur **\<**.  Il n'est pas nécessaire de sélectionner une classe dans la zone **Classes générées** pour supprimer toutes les classes ; en cliquant sur **\<\<**, vous supprimez toutes les classes figurant dans la zone **Classes générées**.  
  
 `Class`  
 Spécifie le nom de la classe sélectionnée dans la zone **Classes générées** que l'Assistant doit ajouter lorsque vous cliquez sur **Terminer**.  Vous pouvez modifier ce nom dans la zone `Class`.  
  
 **fichier .h**  
 Définit le nom du fichier d'en\-tête de la nouvelle classe d'objets.  Par défaut, ce nom est fondé sur le nom que vous avez entré dans la zone **Classes générées**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous sélectionnez un fichier existant, l'Assistant ne l'enregistrera pas à l'emplacement choisi tant que vous n'aurez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d'implémentation pour la nouvelle classe d'objet.  Par défaut, ce nom est fondé sur le nom que vous avez entré dans la zone **Classes générées**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix.  Le fichier n'est pas enregistré à l'emplacement souhaité tant que vous n'avez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous invite à indiquer si l'implémentation de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
## Voir aussi  
 [Ajout d'une classe à partir d'un contrôle ActiveX](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)   
 [Clients Automation : utilisation des bibliothèques de types](../mfc/automation-clients-using-type-libraries.md)