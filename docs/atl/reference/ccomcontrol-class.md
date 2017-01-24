---
title: "CComControl Class | Microsoft Docs"
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
  - "CComControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ambient properties"
  - "CComControl class"
  - "CComControlBase class, CComControl class"
  - "control flags"
  - "controls [ATL], control helper functions"
  - "controls [ATL], propriétés"
  - "propriétés stock, ATL"
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour créer et gérer des contrôles ATL.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
class WinBase= CWindowImpl< T>   
>  
class ATL_NO_VTABLE CComControl :  
public CComControlBase, public WinBase;  
```  
  
#### Paramètres  
 `T`  
 La classe implémentant le contrôle.  
  
 *WinBase*  
 La classe de base qui implémente des fonctions de fenêtrage.  Valeurs par défaut à [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComControl::CComControl](../Topic/CComControl::CComControl.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComControl::ControlQueryInterface](../Topic/CComControl::ControlQueryInterface.md)|Extrait un pointeur vers l'interface demandée.|  
|[CComControl::CreateControlWindow](../Topic/CComControl::CreateControlWindow.md)|Crée une fenêtre pour le contrôle.|  
|[CComControl::FireOnChanged](../Topic/CComControl::FireOnChanged.md)|Informe le récepteur du conteneur qu'une propriété du contrôle a changé.|  
|[CComControl::FireOnRequestEdit](../Topic/CComControl::FireOnRequestEdit.md)|Informe le récepteur du conteneur qu'une propriété de contrôle est sur le point de modifier et que l'objet est demandant au récepteur comment continuer.|  
|[CComControl::MessageBox](../Topic/CComControl::MessageBox.md)|Appelez cette méthode pour créer, afficher, et fonctionner un message.|  
  
## Notes  
 `CComControl` est un ensemble de fonctions d'assistance de contrôle utiles et de membres de données essentielles pour les contrôles ATL.  Lorsque vous créez un contrôle standard ou un contrôle DHTML à l'aide de l'Assistant Contrôle ATL, l'assistant dérivera automatiquement votre classe d' `CComControl`.  `CComControl` dérive la plupart de ses méthodes de [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Pour plus d'informations sur la création d'un contrôle, consultez [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md).  Pour plus d'informations sur l'Assistant Projet ATL, consultez l'article [créer un projet ATL](../../atl/reference/creating-an-atl-project.md).  
  
 Pour une démonstration les méthodes et les données membres d' `CComControl` , consultez l'exemple de [CIRC](../../top/visual-cpp-samples.md) .  
  
## Hiérarchie d'héritage  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComControlBase Class](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl Class](../../atl/reference/ccomcompositecontrol-class.md)