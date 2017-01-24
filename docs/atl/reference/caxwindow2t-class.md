---
title: "CAxWindow2T Class | Microsoft Docs"
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
  - "ATL::CAxWindow2T<TBase>"
  - "ATL::CAxWindow2T"
  - "CAxWindow2T"
  - "ATL.CAxWindow2T<TBase>"
  - "ATL.CAxWindow2T"
  - "CAxWindow2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAxWindow2 class"
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAxWindow2T Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX, et ont également la prise en charge de l'hébergement des contrôles ActiveX autorisés.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <   
class TBase= CWindow   
>  
class CAxWindow2T :   
public CAxWindowT< TBase >  
```  
  
#### Paramètres  
 *TBase*  
 La classe qui `CAxWindowT` dérive de.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAxWindow2T::CAxWindow2T](../Topic/CAxWindow2T::CAxWindow2T.md)|Construit un objet `CAxWindow2T`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAxWindow2T::Create](../Topic/CAxWindow2T::Create.md)|Crée une fenêtre hôte.|  
|[CAxWindow2T::CreateControlLic](../Topic/CAxWindow2T::CreateControlLic.md)|Crée un contrôle ActiveX autorisé, l'initialise, et le héberge dans la fenêtre spécifiée.|  
|[CAxWindow2T::CreateControlLicEx](../Topic/CAxWindow2T::CreateControlLicEx.md)|Crée un contrôle ActiveX autorisé, l'initialise, le héberge dans la fenêtre spécifiée, et extrait un pointeur d'interface \(ou des pointeurs\) du contrôle.|  
|[CAxWindow2T::GetWndClassName](../Topic/CAxWindow2T::GetWndClassName.md)|Méthode statique qui récupère le nom de la classe de fenêtre.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAxWindow2T::operator \=](../Topic/CAxWindow2T::operator%20=.md)|Assigne `HWND` à un objet existant d' `CAxWindow2T` .|  
  
## Notes  
 `CAxWindow2T` fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX.  `CAxWindow2T` a également une prise en charge de l'hébergement des contrôles ActiveX autorisés.  l'hébergement est fourni par « **AtlAxWinLic80** », qui est encapsulé par `CAxWindow2T`.  
  
 La classe `CAxWindow2` est implémentée comme une spécialisation de la classe d' `CAxWindow2T` .  Cette spécialisation est déclarée comme suit :  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
>  Les membres d'`CAxWindowT` sont documentés dans [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 Consultez [Contrôles ActiveX d'hébergement à l'aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise les membres de cette classe.  
  
## Hiérarchie d'héritage  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [FAQ sur la relation contenant\-contenu des contrôles](../../atl/atl-control-containment-faq.md)