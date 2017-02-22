---
title: "Ajout d&#39;objets et de contr&#244;les &#224; un projet ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Contrôle ATL"
  - "projets ATL, ajouter des contrôles"
  - "projets ATL, ajouter des objets"
  - "controls [ATL], ajouter aux projets"
  - "objets (C++), ajouter aux projets ATL"
  - "Assistants (C++), projets ATL"
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Ajout d&#39;objets et de contr&#244;les &#224; un projet ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'un des Assistants Code ATL pour ajouter un objet ou un contrôle à vos projets ATL ou MFC.  Pour chaque objet ou contrôle ajouté, l'Assistant génère des fichiers .cpp et .h, mais aussi un fichier .rgs pour permettre une prise en charge du Registre basée sur les scripts.  Visual Studio fournit les Assistants Code ATL suivants :  
  
||||  
|-|-|-|  
|[Objet simple ATL](../../atl/reference/atl-simple-object-wizard.md)|[Boîte de dialogue ATL](../../atl/reference/atl-dialog-wizard.md)|[Contrôle ATL](../../atl/reference/atl-control-wizard.md)|  
|[Page de propriétés ATL](../../atl/reference/atl-property-page-wizard.md)|[Composant ATL Active Server Page](../../atl/reference/atl-active-server-page-component-wizard.md)|[Consommateur OLE DB ATL](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[Ajout de la prise en charge ATL à votre projet MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[Assistant Composant ATL COM\+ 1.0](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[Fournisseur OLE DB ATL](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  Avant d'ajouter un objet ATL à votre projet, prenez connaissance des données et prérequis le concernant dans les rubriques d'aide connexes.  
  
### Pour ajouter un objet ou un contrôle à l'aide de l'Assistant Contrôle ATL  
  
1.  Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le nœud du projet, puis cliquez sur **Ajouter** dans le menu contextuel.  Cliquez sur **Ajouter une classe**.  
  
     La boîte de dialogue [Ajouter une classe](../../ide/add-class-dialog-box.md) s'affiche.  
  
2.  Le dossier ATL étant sélectionné dans le volet Catégories, sélectionnez l'objet que vous voulez ajouter dans le volet Modèles.  Cliquez sur **Ouvrir**.  L'Assistant Code correspondant à l'objet sélectionné s'affiche.  
  
    > [!NOTE]
    >  Si vous souhaitez ajouter un objet ATL à un projet MFC, vous devez d'abord ajouter une prise en charge ATL au projet existant.  Pour ce faire, suivez les instructions fournies dans [Ajout de la prise en charge ATL à votre projet MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
     Sinon, si vous tentez d'ajouter un objet ATL à votre projet MFC sans avoir au préalable ajouté la prise en charge ATL, Visual Studio vous demande si vous souhaitez ajouter cette prise en charge.  Cliquez sur **Oui** pour ajouter la prise en charge ATL au projet et ouvrir l'Assistant ATL sélectionné.  
  
## Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Types de projets Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Création de projets de bureau à l'aide des Assistants Application](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmation avec ATL et le code C Run\-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)