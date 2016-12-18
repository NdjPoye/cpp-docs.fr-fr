---
title: "Composant ATL COM+&#160;1.0 (Assistant) | Microsoft Docs"
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
  - "vc.codewiz.class.atl.mts.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Composant ATL COM+ 1.0 (Assistant)"
  - "Projets ATL, ajouter des composants"
ms.assetid: 11670681-8671-4122-96a4-2e52f8dadce0
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Composant ATL COM+&#160;1.0 (Assistant)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant pour ajouter un objet à votre projet prenant en charge les services COM\+ 1.0, notamment les transactions.  
  
 Vous pouvez spécifier si l'objet prend en charge les interfaces doubles et l'automation.  Vous pouvez également indiquer la prise en charge de l'interface d'informations sur les erreurs, du contrôle évolué des objets, des transactions et des files d'attente de messages asynchrones.  
  
## Remarques  
 À partir de [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], le script d'inscription produit par cet Assistant inscrira ses composants COM sous **HKEY\_CURRENT\_USER** au lieu de **HKEY\_LOCAL\_MACHINE**.  Pour modifier ce comportement, définissez l'option **Inscrire le composant pour tous les utilisateurs** de l'Assistant ATL.  
  
## Noms  
 Spécifiez les noms de l'objet, de l'interface et des classes à ajouter à votre projet.  À l'exception de la zone **Nom court**, toutes les autres peuvent être modifiées de manière indépendante.  Si vous changez le texte figurant dans la zone **Nom court**, la modification est répercutée au niveau des noms de toutes les autres zones de cette page.  Si vous changez le nom **Coclasse** de la section COM, la modification se répercute dans les zones **Type** et **ProgID**, mais le nom **Interface** demeure inchangé.  Ce mode d'affectation des noms est destiné à faciliter l'identification de tous les noms lorsque vous développez votre contrôle.  
  
 **Nom court**  
 Définit l'abréviation du nom de l'objet.  Le nom que vous entrez détermine le nom de différents éléments \(`Class`, `Coclass`, **fichier .cpp**, **fichier .h**, **Interface**et **Type**\), ainsi que le **ProgID**, sauf si vous modifiez ces champs individuellement.  
  
 **fichier .h**  
 Définit le nom du fichier d'en\-tête de la nouvelle classe d'objets.  Par défaut, ce nom dépend du nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous sélectionnez un fichier existant, l'Assistant ne l'enregistrera pas à l'emplacement choisi tant que vous n'aurez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **Classe**  
 Définit le nom de la classe que vous souhaitez créer.  Ce nom est fondé sur le nom que vous entrez dans la zone **Nom court**, précédé de « C » \(préfixe classique pour un nom de classe\).  
  
 **fichier .cpp**  
 Définit le nom du fichier d'implémentation pour la nouvelle classe d'objet.  Par défaut, ce nom est fondé sur le nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix.  Le fichier n'est pas enregistré à l'emplacement souhaité tant que vous n'avez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous invite à indiquer si l'implémentation de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **Avec attributs**  
 Indique si l'objet utilise des attributs.  Si vous ajoutez un objet à un projet ATL avec attributs, cette option est sélectionnée et ne peut pas être modifiée.  Cela signifie que vous ne pouvez ajouter des objets avec attributs qu'à un projet créé avec la prise en charge des attributs.  
  
 Si vous sélectionnez cette option pour un projet ATL ne prenant pas en charge les attributs, l'Assistant vous invite à spécifier si vous souhaitez ajouter la prise en charge des attributs à ce projet.  
  
 Les objets que vous ajoutez après avoir défini cette option sont désignés avec attributs par défaut \(la case à cocher est activée\).  Vous pouvez désactiver cette case à cocher pour ajouter un objet qui n'utilise pas d'attributs.  
  
 Pour plus d'informations, consultez [Paramètres de l'application, Assistant Projet ATL](../../atl/reference/application-settings-atl-project-wizard.md) et [Mécanismes de base des attributs](../../windows/basic-mechanics-of-attributes.md).  
  
### COM  
 Fournit des informations sur la fonctionnalité COM de l'objet.  
  
 **CoClasse**  
 Définit le nom de la classe de composant contenant une liste des interfaces prises en charge par l'objet.  
  
> [!NOTE]
>  Si vous créez votre projet à l'aide d'attributs ou si vous indiquez sur cette page de l'Assistant que le composant COM\+ 1.0 utilise des attributs, vous ne pouvez alors pas modifier cette option, car ATL ne contient pas l'attribut `coclass`.  
  
 **Tapez**  
 Définit la description de l'objet qui s'affiche dans le Registre.  
  
 **Interface**  
 Définit l'interface que vous créez pour votre objet.  Cette interface contient vos méthodes personnalisées.  
  
 **ProgID**  
 Définit le nom que les conteneurs peuvent utiliser à la place de l'identificateur CLSID de l'objet.  
  
## Voir aussi  
 [ATL COM\+ 1.0 Component](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)