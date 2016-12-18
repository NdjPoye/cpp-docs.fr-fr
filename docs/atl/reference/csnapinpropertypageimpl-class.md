---
title: "CSnapInPropertyPageImpl Class | Microsoft Docs"
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
  - "CSnapInPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInPropertyPageImpl class"
  - "pages de propriétés, ATL"
  - "snap-ins"
  - "snap-ins, pages de propriétés"
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSnapInPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour implémenter un objet page de propriétés de composant logiciel enfichable.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
CSnapInPropertyPageImpl : public CDialogImplBase  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](../Topic/CSnapInPropertyPageImpl::CSnapInPropertyPageImpl.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](../Topic/CSnapInPropertyPageImpl::CancelToClose.md)|Modifie l'état des boutons **OK** et de **Annuler** .|  
|[CSnapInPropertyPageImpl::Create](../Topic/CSnapInPropertyPageImpl::Create.md)|Initialise un objet nouvellement créé d' `CSnapInPropertyPageImpl` .|  
|[CSnapInPropertyPageImpl::OnApply](../Topic/CSnapInPropertyPageImpl::OnApply.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton **Appliquer maintenant** lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CSnapInPropertyPageImpl::OnHelp](../Topic/CSnapInPropertyPageImpl::OnHelp.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de **Aide** lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CSnapInPropertyPageImpl::OnKillActive](../Topic/CSnapInPropertyPageImpl::OnKillActive.md)|Appelé par l'infrastructure lorsque la page actuelle n'est plus active.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](../Topic/CSnapInPropertyPageImpl::OnQueryCancel.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de **Annuler** et avant que l'annulation a eu lieu.|  
|[CSnapInPropertyPageImpl::OnReset](../Topic/CSnapInPropertyPageImpl::OnReset.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de **Réinitialiser** lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CSnapInPropertyPageImpl::OnSetActive](../Topic/CSnapInPropertyPageImpl::OnSetActive.md)|Appelé par l'infrastructure lorsque la page actuelle devient active.|  
|[CSnapInPropertyPageImpl::OnWizardBack](../Topic/CSnapInPropertyPageImpl::OnWizardBack.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton précédent lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](../Topic/CSnapInPropertyPageImpl::OnWizardFinish.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton de **Finish** lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CSnapInPropertyPageImpl::OnWizardNext](../Topic/CSnapInPropertyPageImpl::OnWizardNext.md)|Appelé par l'infrastructure lorsque l'utilisateur clique sur le bouton d' `Next` lorsque vous utilisez une feuille de propriétés de type assistant.|  
|[CSnapInPropertyPageImpl::QuerySiblings](../Topic/CSnapInPropertyPageImpl::QuerySiblings.md)|Transféré au message actuellement toutes les pages de la feuille de propriétés.|  
|[CSnapInPropertyPageImpl::SetModified](../Topic/CSnapInPropertyPageImpl::SetModified.md)|Appelez pour l'activation ou mettre le bouton **Appliquer maintenant** .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSnapInPropertyPageImpl::m\_psp](../Topic/CSnapInPropertyPageImpl::m_psp.md)|La structure de **PROPSHEETPAGE** windows utilisée par l'objet d' `CSnapInPropertyPageImpl` .|  
  
## Notes  
 `CSnapInPropertyPageImpl` fournit une implémentation de base d'un objet page de propriétés de composant logiciel enfichable.  Les fonctionnalités de base d'une page de propriétés de composant logiciel enfichable sont implémentées à l'aide de plusieurs interfaces et mappent des types.  
  
## Hiérarchie d'héritage  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## Configuration requise  
 **Header:** atlsnap.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)