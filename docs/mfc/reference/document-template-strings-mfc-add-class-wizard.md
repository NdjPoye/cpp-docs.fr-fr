---
title: "Cha&#238;nes du mod&#232;le de document, Assistant Ajouter une classe MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.simple.doctemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Ajouter une classe MFC, chaînes de contrôle de document"
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Cha&#238;nes du mod&#232;le de document, Assistant Ajouter une classe MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette page de l'Assistant est disponible uniquement pour les classes répondant aux critères suivants :  
  
-   Le projet MFC prend en charge l'architecture Document\/Vue.  
  
-   La classe de base de la nouvelle classe est [CFormView](../../mfc/reference/cformview-class.md).  
  
-   La case à cocher **Générer des ressources DocTemplate** est activée dans la section **Noms** de l'[Assistant Classe MFC](../../mfc/reference/mfc-add-class-wizard.md).  
  
 L'Assistant propose les valeurs par défaut suivantes pour vous aider à créer, gérer et traduire des vues de formulaires.  Comme la plupart des chaînes modèles de document sont visibles et sont employées par les utilisateurs des formulaires, elles sont traduites dans la **Langue des ressources** indiquée à la page [Types d'applications](../../mfc/reference/application-type-mfc-application-wizard.md) de l'Assistant Application MFC au moment de la création du projet.  
  
> [!NOTE]
>  L'Assistant n'assure pas la prise en charge automatique de l'impression pour les classes dérivées de `CFormView`.  
  
 Pour plus d'informations, consultez [Modèles de document et processus de création document\/vue](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Chaînes non localisées  
 S'applique aux applications créant des documents utilisateur.  Les utilisateurs peuvent ouvrir et enregistrer des documents plus facilement si le type de document a une extension de fichier et un ID de type de fichier.  Ces éléments ne sont pas traduits parce qu'ils sont utilisés par le système, et non pas par l'utilisateur.  
  
 **Extension du fichier**  
 Définit l'extension de fichier associée au type de document pour cette application de formulaires.  L'extension de fichier par défaut est fondée sur le nom de la classe.  Par exemple, si la nouvelle classe MFC est appelée **CWidget**, l'extension de fichier par défaut est .wid.  L'extension de fichier est utilisée dans les filtres de fichiers, ainsi que dans les boîtes de dialogue **Ouvrir** et **Enregistrer sous**.  
  
 Si vous modifiez l'extension de fichier, le changement se répercute dans la zone **Nom du filtre**.  
  
> [!NOTE]
>  Si vous modifiez l'extension de fichier par défaut, n'ajoutez pas de point.  
  
 **ID du type de fichier**  
 Définit l'étiquette du type de document dans la base de registres.  
  
## Chaînes localisées  
 Génère des chaînes associées aux formulaires et documents qui sont lus et utilisés par les utilisateurs de l'application. Par conséquent, ces chaînes sont traduites.  
  
 **Nom de type de document**  
 Identifie le type de document sous lequel un document de l'application peut être regroupé.  Par défaut, il est fondé sur le nom de la classe.  Par exemple, si la nouvelle classe MFC est appelée **CWidget**, le nom du type de document par défaut est Widget.  Le changement de la valeur par défaut n'entraîne la modification d'aucune autre option de la boîte de dialogue.  
  
 **Nom de filtre**  
 Définit le nom que les utilisateurs peuvent indiquer pour rechercher les fichiers du type de fichier spécifié.  Cette option est disponible à partir des options **Type** et **Type** dans les boîtes de dialogue **Ouvrir** et **Enregistrer sous** Windows standard.  Par défaut, ce nom est fondé sur le nom du projet, plus Files, suivi de l'extension indiquée dans **Extension du fichier**.  Par exemple, si votre projet porte le nom Widget et si son extension de fichier est .wid, le **Nom du filtre** par défaut est Widget Files \(\*.wid\).  
  
 **Nom court de nouveau fichier**  
 Définit le nom qui s'affiche dans la boîte de dialogue `New` standard de Windows, à condition que le projet possède plusieurs modèles de documents.  Si votre application est un [serveur Automation](../../mfc/automation-servers.md), ce nom est utilisé en tant que nom court de votre objet Automation.  Par défaut, ce nom est fondé sur le nom de la classe.  
  
 **Nom long du type de fichier**  
 Définit le nom de type de fichier dans la base de registres.  Si votre application est un serveur Automation, ce nom est utilisé en tant que nom long de votre objet Automation.  Par défaut, ce nom est fondé sur le nom de la classe, plus .Document.  Par exemple, si le nom de la classe est **CWidget**, le **Nom long du type de fichier** est Widget Document.  
  
 **Classe de document**  
 Indique la classe de document du projet.  Par défaut, il s'agit de la classe de document de l'application principale, comme décrit à la page [Consultation des classes générées](../../mfc/reference/generated-classes-mfc-application-wizard.md) de l'Assistant Application MFC.  Si vous avez ajouté d'autres classes de documents au projet, vous pouvez sélectionner une autre classe de document dans la liste.  
  
## Voir aussi  
 [Assistant Ajouter une classe MFC](../../mfc/reference/mfc-add-class-wizard.md)   
 [MFC, classe](../../mfc/reference/adding-an-mfc-class.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)