---
title: "CSnapInItemImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSnapInItemImpl"
  - "ATL.CSnapInItemImpl"
  - "ATL::CSnapInItemImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInItemImpl class"
  - "snap-ins"
  - "snap-ins, ATL support for"
  - "snap-ins, data items"
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSnapInItemImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour implémenter un objet de nœud de composant logiciel enfichable.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
BOOL bIsExtension= FALSE  
>  
class ATL_NO_VTABLE CSnapInItemImpl :  
public CSnapInItem  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **TRUE** si l'objet est une extension de composant logiciel enfichable ; sinon **FALSE**.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](../Topic/CSnapInItemImpl::CSnapInItemImpl.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](../Topic/CSnapInItemImpl::AddMenuItems.md)|Ajoute des éléments de menu dans un menu contextuel.|  
|[CSnapInItemImpl::Command](../Topic/CSnapInItemImpl::Command.md)|Appelé par la console lorsqu'un élément de menu personnalisé est sélectionné.|  
|[CSnapInItemImpl::CreatePropertyPages](../Topic/CSnapInItemImpl::CreatePropertyPages.md)|Ajoute des pages à la feuille de propriétés de composant logiciel enfichable.|  
|[CSnapInItemImpl::FillData](../Topic/CSnapInItemImpl::FillData.md)|Copie les informations sur l'objet enfichable dans un flux spécifié.|  
|[CSnapInItemImpl::GetResultPaneInfo](../Topic/CSnapInItemImpl::GetResultPaneInfo.md)|Extrait la structure de **RESULTDATAITEM** de le composant logiciel enfichable.|  
|[CSnapInItemImpl::GetResultViewType](../Topic/CSnapInItemImpl::GetResultViewType.md)|Détermine le type de vue utilisé par le volet de résultats.|  
|[CSnapInItemImpl::GetScopePaneInfo](../Topic/CSnapInItemImpl::GetScopePaneInfo.md)|Extrait la structure de **SCOPEDATAITEM** de le composant logiciel enfichable.|  
|[CSnapInItemImpl::Notify](../Topic/CSnapInItemImpl::Notify.md)|Appelé par la console pour informer le composant logiciel enfichable des actions prises par l'utilisateur.|  
|[CSnapInItemImpl::QueryPagesFor](../Topic/CSnapInItemImpl::QueryPagesFor.md)|Appelé pour voir si le nœud de composant logiciel enfichable prend en charge les pages de propriétés.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](../Topic/CSnapInItemImpl::SetMenuInsertionFlags.md)|Modifie les balises d'insertion de menu pour un objet enfichable.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](../Topic/CSnapInItemImpl::SetToolbarButtonInfo.md)|Définit les informations du bouton de barre d'outils spécifié.|  
|[CSnapInItemImpl::UpdateMenuState](../Topic/CSnapInItemImpl::UpdateMenuState.md)|Met à jour l'état d'un élément de menu contextuel.|  
|[CSnapInItemImpl::UpdateToolbarButton](../Topic/CSnapInItemImpl::UpdateToolbarButton.md)|Met à jour l'état du bouton de barre d'outils spécifié.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSnapInItemImpl::m\_bstrDisplayName](../Topic/CSnapInItemImpl::m_bstrDisplayName.md)|Le nom de l'objet enfichable.|  
|[CSnapInItemImpl::m\_resultDataItem](../Topic/CSnapInItemImpl::m_resultDataItem.md)|La structure de **RESULTDATAITEM** windows utilisée par l'objet d' `CSnapInItemImpl` .|  
|[CSnapInItemImpl::m\_scopeDataItem](../Topic/CSnapInItemImpl::m_scopeDataItem.md)|La structure de **SCOPEDATAITEM** windows utilisée par l'objet d' `CSnapInItemImpl` .|  
  
## Notes  
 `CSnapInItemImpl` fournit une implémentation de base d'un objet de nœud de composant logiciel enfichable, par exemple ajouter des éléments de menu et des barres d'outils, et transférer des commandes pour le nœud de composant logiciel enfichable à la fonction gestionnaire appropriée.  Ces fonctionnalités sont implémentées à l'aide de plusieurs interfaces et mappent des types.  Les notifications par défaut de handles d'implémentation envoyées à l'objet de nœud pour déterminer l'instance appropriée dans la classe dérivée et en effectuant le suivi du message à l'instance appropriée.  
  
## Hiérarchie d'héritage  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## Configuration requise  
 **Header:** atlsnap.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)