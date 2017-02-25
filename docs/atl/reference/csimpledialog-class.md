---
title: "CSimpleDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleDialog"
  - "CSimpleDialgo"
  - "CSimpleDialog"
  - "ATL.CSimpleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleDialog class"
  - "CSimpleDialog class, modal dialog boxes in ATL"
  - "boîtes de dialogue, modales"
  - "boîtes de dialogue modales, ATL"
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente une boîte de dialogue modale de base.  
  
## Syntaxe  
  
```  
  
      template <  
   WORD t_wDlgTemplateID,  
   BOOL t_bCenter = TRUE  
>  
class CSimpleDialog :  
   public CDialogImplBase  
```  
  
#### Paramètres  
 *t\_wDlgTemplateID*  
  
 l'ID de ressource de la ressource modèle de boîte de dialogue.  
  
 *t\_bCenter*  
 **TRUE** si l'objet dialog doit être centré sur la fenêtre propriétaire ; sinon **FALSE**.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleDialog::DoModal](../Topic/CSimpleDialog::DoModal.md)|Crée une boîte de dialogue modale.|  
  
## Notes  
 Implémente une boîte de dialogue modale avec la fonctionnalité de base.  `CSimpleDialog` fournit la prise en charge des contrôles communs Windows uniquement.  Pour créer et afficher une boîte de dialogue modale, créez une instance de cette classe, en fournissant le nom d'un modèle existant de ressource pour la boîte de dialogue.  L'objet de boîte de dialogue se ferme lorsque l'utilisateur clique sur un contrôle avec une valeur prédéfinie \(par exemple IDOK ou IDCANCEL\).  
  
 `CSimpleDialog` vous permet de créer uniquement des boîtes de dialogue modale.  `CSimpleDialog` fournit la procédure de boîte de dialogue, qui utilise la table des messages par défaut pour exécuter des messages aux gestionnaires appropriés.  
  
 Consultez l' [implémenter une boîte de dialogue](../../atl/implementing-a-dialog-box.md) pour plus d'informations.  
  
## Hiérarchie d'héritage  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)