---
title: "CComCompositeControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComCompositeControl"
  - "ATL::CComCompositeControl"
  - "ATL.CComCompositeControl<T>"
  - "ATL.CComCompositeControl"
  - "ATL::CComCompositeControl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCompositeControl class"
  - "contrôles composites, CComCompositeControl class"
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComCompositeControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit les méthodes requises pour implémenter un contrôle composite.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T   
>  
class CComCompositeControl :  
public CComControl< T, CAxDialogImpl< T > >  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que de toutes les autres interfaces vous souhaitez prendre en charge pour votre contrôle composite.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCompositeControl::CComCompositeControl](../Topic/CComCompositeControl::CComCompositeControl.md)|Constructeur.|  
|[CComCompositeControl::~CComCompositeControl](../Topic/CComCompositeControl::~CComCompositeControl.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md)|Appelez cette méthode pour avertir ou unadvise tous les contrôles hébergés par le contrôle composite.|  
|[CComCompositeControl::CalcExtent](../Topic/CComCompositeControl::CalcExtent.md)|Appelez cette méthode pour calculer la taille en unités HIMETRIC de la ressource de boîte de dialogue utilisée pour héberger le contrôle composite.|  
|[CComCompositeControl::Create](../Topic/CComCompositeControl::Create.md)|Cette méthode est appelée pour créer la fenêtre de contrôle du contrôle composite.|  
|[CComCompositeControl::CreateControlWindow](../Topic/CComCompositeControl::CreateControlWindow.md)|Appelez cette méthode pour créer la fenêtre du contrôle et pour notifier tout contrôle hébergé.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](../Topic/CComCompositeControl::SetBackgroundColorFromAmbient.md)|Appelez cette méthode pour définir la couleur d'arrière\-plan du contrôle composite à la couleur d'arrière\-plan du conteneur.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCompositeControl::m\_hbrBackground](../Topic/CComCompositeControl::m_hbrBackground.md)|Pinceau d'arrière\-plan.|  
|[CComCompositeControl::m\_hWndFocus](../Topic/CComCompositeControl::m_hWndFocus.md)|Handle de la fenêtre qui a actuellement le focus.|  
  
## Notes  
 Les classes dérivées de la classe `CComCompositeControl` héritent les fonctionnalités d'un contrôle composite ActiveX.  Les contrôles ActiveX dérivés d' `CComCompositeControl` sont hébergés par une boîte de dialogue standard.  Ces types de contrôles sont appelés des contrôles composites car ils peuvent héberger d'autres contrôles \(contrôles natifs de contrôles Windows et ActiveX\).  
  
 `CComCompositeControl` identifie la ressource de boîte de dialogue à utiliser lors de la création du contrôle composite en recherchant une donnée membre énumérée dans la classe enfant.  Le membre IDD de cette classe enfant a pour valeur l'ID de ressource de la ressource de boîte de dialogue qui sera utilisée comme fenêtre de contrôle.  Voici un exemple des données membres que la classe dérivée d' `CComCompositeControl` doit contenir pour identifier la ressource de boîte de dialogue à utiliser pour la fenêtre du contrôle :  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/CPP/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Les contrôles composites sont toujours les contrôles fenêtrés, bien qu'ils puissent contenir des contrôles sans fenêtre.  
  
 Un contrôle implémenté par `CComCompositeControl`\- la classe dérivée a le comportement de tabulation par défaut incorporé.  Lorsque le contrôle reçoit le focus en étant tabulé dans une application conteneur, appuyez sur la touche TAB successivement entraîne le focus d'être défilé via les contrôles contenus de tout le contrôle composite, puis du contrôle composite et en fonction à l'élément suivant dans l'ordre de tabulation du conteneur.  L'ordre de tabulation des contrôles hébergés est déterminé par la ressource de boîte de dialogue et détermine l'ordre dans lequel la tabulation se produit.  
  
> [!NOTE]
>  Pour que les accélérateurs fonctionnent correctement avec `CComCompositeControl`, il est nécessaire de charger une table d'accélérateurs lorsque le contrôle est créé, passez le handle et le nombre d'accélérateurs dans le en [IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md), et perdent enfin la table lorsque le contrôle est libéré.  
  
## Exemple  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/CPP/ccomcompositecontrol-class_2.h)]  
  
## Hiérarchie d'héritage  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Notions de base des contrôles composites](../../atl/atl-composite-control-fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)