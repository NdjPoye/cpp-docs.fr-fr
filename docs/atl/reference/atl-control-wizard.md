---
title: "Assistant Contr&#244;le ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.control.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Contrôle ATL"
  - "projets ATL, ajouter des contrôles"
  - "controls [ATL], ajouter aux projets"
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
caps.latest.revision: 17
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Contr&#244;le ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Insère dans un projet ATL \(ou un projet MFC avec la prise en charge ATL\) un contrôle ATL.  Vous pouvez utiliser cet Assistant pour insérer l'un des trois types de contrôles :  
  
-   Contrôle standard  
  
-   Contrôle composite  
  
-   Contrôle DHTML  
  
 En outre, vous pouvez spécifier un contrôle minimal en supprimant de la liste [Interfaces](../../atl/reference/interfaces-atl-control-wizard.md) les interfaces proposées par défaut pour que les contrôles les ouvrent dans la plupart des conteneurs.  Vous pouvez définir les interfaces que le contrôle doit prendre en charge à la page **Interfaces** de l'Assistant.  
  
## Remarques  
 Le script d'inscription produit par cet Assistant enregistrera ses composants COM sous HKEY\_CURRENT\_USER au lieu de HKEY\_LOCAL\_MACHINE.  Pour modifier ce comportement, définissez l'option **Inscrire le composant pour tous les utilisateurs** de l'Assistant ATL.  
  
## Noms  
 Spécifiez les noms de l'objet, de l'interface et des classes à ajouter à votre projet.  À l'exception de **Nom court**, toutes les autres zones peuvent être modifiées indépendamment.  Si vous changez le texte figurant dans la zone **Nom court**, la modification est répercutée au niveau des noms de toutes les autres zones de cette page.  Si vous changez le nom **Coclasse** de la section COM, cette modification est répercutée dans la zone **Type**, mais le nom figurant dans la zone **Interface** et **ProgID** demeure inchangé.  Ce mode d'affectation des noms est destiné à faciliter l'identification de tous les noms lorsque vous développez votre contrôle.  
  
> [!NOTE]
>  La **coclasse** ne peut être modifiée que pour les contrôles sans attributs.  Si votre projet est avec attributs, vous ne pouvez pas modifier la **coclasse**.  
  
### C\+\+  
 Fournit des informations à la classe C\+\+ créée pour implémenter l'objet.  
  
 **Nom court**  
 Définit l'abréviation du nom de l'objet.  Le nom que vous entrez détermine la classe et les noms **Coclasse**, les noms de fichiers \(.CPP et .H\), le nom d'interface et les noms de **Type**, sauf si vous modifiez ces champs individuellement.  
  
 **Classe**  
 Définit le nom de la classe qui implémente l'objet.  Ce nom dépend du nom que vous entrez dans la zone **Nom court**, précédé de « C » \(préfixe classique pour un nom de classe\).  
  
 **fichier .h**  
 Définit le nom du fichier d'en\-tête de la nouvelle classe d'objets.  Par défaut, ce nom dépend du nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant.  Si vous sélectionnez un fichier existant, l'Assistant ne l'enregistrera pas à l'emplacement choisi tant que vous n'aurez pas cliqué sur **Terminer**.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous demande d'indiquer si la déclaration de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d'implémentation pour la nouvelle classe d'objet.  Par défaut, ce nom dépend du nom que vous entrez dans la zone **Nom court**.  Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l'emplacement de votre choix.  Le fichier n'est pas enregistré à l'emplacement souhaité tant que vous n'avez pas cliqué sur **Terminer** dans l'Assistant.  
  
 L'Assistant n'écrase pas un fichier.  Si vous sélectionnez le nom d'un fichier existant et cliquez sur **Terminer**, l'Assistant vous invite à indiquer si l'implémentation de classe doit être ajoutée au contenu du fichier.  Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **Non** pour revenir à l'Assistant et spécifier un autre nom de fichier.  
  
 **Avec attributs**  
 Indique si l'objet utilise des attributs.  Si vous ajoutez un objet à un projet ATL avec attributs, cette option est sélectionnée et ne peut pas être modifiée.  Cela signifie que vous ne pouvez ajouter des objets avec attributs qu'à un projet créé avec la prise en charge des attributs.  
  
 Vous ne pouvez ajouter un objet avec attributs qu'à un projet ATL utilisant des attributs.  Si vous sélectionnez cette option pour un projet ATL ne prenant pas en charge les attributs, l'Assistant vous invite à spécifier si vous souhaitez ajouter la prise en charge des attributs à ce projet.  
  
 Les objets que vous ajoutez après avoir défini cette option sont désignés par défaut comme étant avec attributs \(la case à cocher correspondante est activée\).  Vous pouvez désactiver cette case à cocher pour ajouter un objet qui n'utilise pas d'attributs.  
  
 Pour plus d'informations, consultez [Paramètres de l'application, Assistant Projet ATL](../../atl/reference/application-settings-atl-project-wizard.md) et [Mécanismes de base des attributs](../../windows/basic-mechanics-of-attributes.md).  
  
### COM  
 Fournit des informations sur la fonctionnalité COM de l'objet.  
  
 **CoClasse**  
 Définit le nom de la classe de composant contenant une liste des interfaces prises en charge par l'objet.  
  
> [!NOTE]
>  Si vous créez votre projet à l'aide d'attributs ou si vous indiquez sur cette page de l'Assistant que le contrôle utilise des attributs, cette option ne peut pas être modifiée, car ATL ne contient pas l'attribut **coclass**.  
  
 **Interface**  
 Définit le nom de l'interface de l'objet.  Un nom d'interface est précédé par défaut de « I ».  
  
 **Tapez**  
 Définit la description de l'objet qui s'affiche dans le Registre.  
  
 **ProgID**  
 Définit le nom que les conteneurs peuvent utiliser à la place de l'identificateur CLSID de l'objet.  Ce champ n'est pas rempli automatiquement.  Si vous ne remplissez pas ce champ manuellement, le contrôle ne peut pas être disponible à d'autres outils.  Par exemple, les contrôles ActiveX générés sans un `ProgID` ne sont pas disponibles dans la boîte de dialogue **Insérer un contrôle ActiveX**.  Pour plus d'informations sur cette boîte de dialogue, consultez [Insérer un contrôle ActiveX, boîte de dialogue](../../mfc/insert-activex-control-dialog-box.md).  
  
## Voir aussi  
 [ATL Control](../../atl/reference/adding-an-atl-control.md)   
 [Adding Functionality to the Composite Control](../../atl/adding-functionality-to-the-composite-control.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)