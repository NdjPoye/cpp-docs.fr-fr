---
title: "Assistant Page de propri&#233;t&#233;s ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.ppg.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Projets ATL, ajouter des pages de propriétés"
  - "Assistant Page de propriétés ATL"
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Assistant Page de propri&#233;t&#233;s ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet Assistant [ajoute une page de propriétés dans un projet ATL](../../atl/reference/adding-an-atl-property-page.md) ou dans un projet MFC prenant en charge ATL.  Une page de propriétés ATL fournit une interface utilisateur permettant de définir les propriétés \(ou d'appeler les méthodes\) d'un ou plusieurs objets COM.  
  
## Remarques  
 À partir de [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], le script d'inscription produit par cet Assistant inscrira ses composants COM sous **HKEY\_CURRENT\_USER** au lieu de **HKEY\_LOCAL\_MACHINE**.  Pour modifier ce comportement, définissez l'option **Inscrire le composant pour tous les utilisateurs** de l'Assistant ATL.  
  
## Noms  
 Spécifiez les noms de l'objet, de l'interface et des classes à ajouter à votre projet.  À l'exception de **Nom court**, toutes les zones peuvent être modifiées indépendamment les unes des autres.  Si vous changez le texte figurant dans la zone **Nom court**, la modification est répercutée au niveau des noms de toutes les autres zones de cette page.  Si vous changez le nom figurant dans la zone **Coclass** de la section COM, cette modification a des répercussions dans les zones **Type** et **ProgID**.  Ce mode d'affectation des noms est destiné à faciliter l'identification de tous les noms lorsque vous développez votre page de propriétés.  
  
> [!NOTE]
>  La **coclasse** ne peut être modifiée que pour les projets sans attributs.  Si votre projet est avec attributs, vous ne pouvez pas modifier la **coclasse**.  
  
### C\+\+  
 Fournit des informations à la classe C\+\+ créée pour implémenter l'objet.  
  
|||  
|-|-|  
|Terme|Définition|  
|**Nom court**|Définit l'abréviation du nom de l'objet.  Le nom que vous entrez détermine la classe et les noms de **Cocasse**, les noms de fichiers \(**.cpp** et **.h**\), le nom **Type** et le **ProgID**, sauf si vous modifiez ces champs individuellement.|  
|**fichier .h**|Définit le nom du fichier d'en\-tête de la nouvelle classe d'objets.  Par défaut, ce nom dépend du nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous sélectionnez un fichier existant, l'Assistant ne l'enregistrera pas à l'emplacement choisi tant que vous n'aurez pas cliqué sur **Terminer** dans l'Assistant.<br /><br /> L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.|  
|**Classe**|Définit le nom de la classe qui implémente l'objet.  Ce nom dépend du nom que vous entrez dans la zone **Nom court**, précédé de « C » \(préfixe classique pour un nom de classe\).|  
|**fichier .cpp**|Définit le nom du fichier d'implémentation pour la nouvelle classe d'objet.  Par défaut, ce nom dépend du nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix.  Le fichier n'est pas enregistré à l'emplacement souhaité tant que vous n'avez pas cliqué sur **Terminer** dans l'Assistant.<br /><br /> L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous invite à indiquer si l'implémentation de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.|  
|**Avec attributs**|Indique si l'objet utilise des attributs.  Si vous ajoutez un objet à un projet ATL avec attributs, cette option est sélectionnée et ne peut pas être modifiée. Autrement dit, vous ne pouvez ajouter des objets avec attributs qu'à un projet créé avec la prise en charge des attributs.<br /><br /> Vous ne pouvez ajouter un objet avec attributs qu'à un projet ATL utilisant des attributs.  Si vous sélectionnez cette option pour un projet ATL ne prenant pas en charge les attributs, l'Assistant vous invite à spécifier si vous souhaitez ajouter la prise en charge des attributs à ce projet.<br /><br /> Les objets que vous ajoutez après avoir défini cette option sont désignés par défaut comme étant avec attributs \(la case à cocher correspondante est activée\).  Vous pouvez désactiver cette case à cocher pour ajouter un objet qui n'utilise pas d'attributs.<br /><br /> Pour plus d'informations, consultez [Paramètres de l'application, Assistant Projet ATL](../../atl/reference/application-settings-atl-project-wizard.md) et [Mécanismes de base des attributs](../../windows/basic-mechanics-of-attributes.md).|  
  
### COM  
 Fournit des informations sur la fonctionnalité COM de l'objet.  
  
 **CoClasse**  
 Définit le nom de la classe de composant contenant une liste des interfaces prises en charge par l'objet.  
  
> [!NOTE]
>  Si vous créez votre projet à l'aide d'attributs ou si vous indiquez sur cette page de l'Assistant que la page de propriétés utilise des attributs, vous ne pouvez alors pas modifier cette option, car ATL ne contient pas l'attribut `coclass`.  
  
 **Tapez**  
 Définit la description de l'objet qui s'affiche dans le Registre.  
  
 **ProgID**  
 Définit le nom que les conteneurs peuvent utiliser à la place de l'identificateur CLSID de l'objet.  
  
## Voir aussi  
 [Options, Assistant Page de propriétés ATL](../../atl/reference/options-atl-property-page-wizard.md)   
 [Chaînes, Assistant Page de propriétés ATL](../../atl/reference/strings-atl-property-page-wizard.md)   
 [Example: Implementing a Property Page](../../atl/example-implementing-a-property-page.md)