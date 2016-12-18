---
title: "CAxDialogImpl Class | Microsoft Docs"
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
  - "ATL::CAxDialogImpl"
  - "ATL.CAxDialogImpl"
  - "CAxDialogImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, boîtes de dialogue"
  - "CAxDialogImpl class"
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAxDialogImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente une boîte de dialogue \(modale ou non modale\) que des contrôles ActiveX d'hôtes.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
class TBase= CWindow  
>  
class ATL_NO_VTABLE CAxDialogImpl :  
public CDialogImplBaseT< TBase>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `CAxDialogImpl`.  
  
 *TBase*  
 La classe de fenêtre de base pour **CDialogImplBaseT**.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](../Topic/CAxDialogImpl::AdviseSinkMap.md)|Appelez cette méthode pour avertir ou unadvise toutes les entrées dans la table d'événements de mappage du récepteur de l'objet.|  
|[CAxDialogImpl::Create](../Topic/CAxDialogImpl::Create.md)|Appelez cette méthode pour créer une boîte de dialogue non modale.|  
|[CAxDialogImpl::DestroyWindow](../Topic/CAxDialogImpl::DestroyWindow.md)|Appelez cette méthode pour détruire une boîte de dialogue non modale.|  
|[CAxDialogImpl::DoModal](../Topic/CAxDialogImpl::DoModal.md)|Appelez cette méthode pour créer une boîte de dialogue modale.|  
|[CAxDialogImpl::EndDialog](../Topic/CAxDialogImpl::EndDialog.md)|Appelez cette méthode pour détruire une boîte de dialogue modale.|  
|[CAxDialogImpl::GetDialogProc](../Topic/CAxDialogImpl::GetDialogProc.md)|Appelez cette méthode pour obtenir un pointeur vers une fonction de rappel d' `DialogProc` .|  
|[CAxDialogImpl::GetIDD](../Topic/CAxDialogImpl::GetIDD.md)|Appelez cette méthode pour obtenir l'ID de ressource modèle de boîte de dialogue|  
|[CAxDialogImpl::IsDialogMessage](../Topic/CAxDialogImpl::IsDialogMessage.md)|Appelez cette méthode pour déterminer si un message est prévu pour cette boîte de dialogue et, s'il est, traite le message.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAxDialogImpl::m\_bModal](../Topic/CAxDialogImpl::m_bModal.md)|Une variable qui existe uniquement dans les versions debug et a la valeur true si la boîte de dialogue est modale.|  
  
## Notes  
 `CAxDialogImpl` vous permet de créer un modal ou une boîte de dialogue non modale.  `CAxDialogImpl` fournit la procédure de boîte de dialogue, qui utilise la table des messages par défaut pour exécuter des messages aux gestionnaires appropriés.  
  
 `CAxDialogImpl` dérive d' `CDialogImplBaseT`, qui dérive *de TBase* \(par défaut, `CWindow`\) et d' `CMessageMap`.  
  
 Votre classe doit définir un membre d'IDD qui spécifie l'ID de ressource modèle de boîte de dialogue  Par exemple, ajouter un objet dialog ATL à l'aide de la boîte de dialogue **ajoutez la classe** ajoute automatiquement la ligne suivante à votre classe :  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/CPP/caxdialogimpl-class_1.h)]  
  
 où `MyDialog` est **Nom court** présenté dans l'Assistant Dialogue ATL.  
  
 Consultez l' [implémenter une boîte de dialogue](../../atl/implementing-a-dialog-box.md) pour plus d'informations.  
  
 Notez qu'un contrôle ActiveX sur une boîte de dialogue modale créée avec `CAxDialogImpl` ne prendra pas en charge les touches accélérateur.  Pour prendre en charge des touches accélérateur sur une boîte de dialogue créée avec `CAxDialogImpl`, créez une boîte de dialogue non modale et, à l'aide de votre propre boucle de message, utilisez [CAxDialogImpl::IsDialogMessage](../Topic/CAxDialogImpl::IsDialogMessage.md) après avoir reçu un message de la file d'attente gérer une touche accélérateur.  
  
 Pour plus d'informations sur `CAxDialogImpl`, consultez [FAQ de contenance de contrôles ATL](../../atl/atl-control-containment-faq.md).  
  
## Hiérarchie d'héritage  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [CDialogImpl Class](../../atl/reference/cdialogimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)