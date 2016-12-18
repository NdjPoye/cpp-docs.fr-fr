---
title: "IAxWinAmbientDispatchEx Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IAxWinAmbientDispatchEx"
  - "IAxWinAmbientDispatchEx"
  - "ATL::IAxWinAmbientDispatchEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatchEx interface"
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinAmbientDispatchEx Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette interface implémente les propriétés ambiantes supplémentaires pour un contrôle hébergé.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      MIDL_INTERFACE( "B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5" )  
IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[SetAmbientDispatch](../Topic/IAxWinAmbientDispatchEx::SetAmbientDispatch.md)|Cette méthode est appelée pour remplir l'interface par défaut de la propriété ambiante avec une interface définie par l'utilisateur.|  
  
## Notes  
 Incluez cette interface dans les applications ATL qui sont statiquement liées à ATL et hébergent des contrôles ActiveX, notamment les contrôles ActiveX possédant des propriétés ambiantes.  Sans cette interface génère cette assertion : « Vous avez oublié de passer le LIBID à CComModule::Init ? »  
  
 Cette interface est exposée par le contrôle ActiveX ATL hébergement d'objets.  Dérivé d' [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` ajoute une méthode qui permet de remplir l'interface de propriété ambiante fournie par ATL avec un de vos propres.  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) essaiera de charger les informations de type à propos de `IAxWinAmbientDispatch` et d' `IAxWinAmbientDispatchEx` de la bibliothèque de types qui contient le code.  
  
 Si vous liez à ATL90.dll, **AXHost** charge des informations de type de la bibliothèque de types dans la DLL.  
  
 Consultez [Contrôles ActiveX d'hébergement à l'aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour plus de détails.  
  
## Configuration requise  
 La définition de cette interface est disponible sous plusieurs formes, comme indiqué dans le tableau suivant.  
  
|Type de définition|Fichier|  
|------------------------|-------------|  
|IDL|atliface.idl|  
|Bibliothèque de types|ATL.dll|  
|C\+\+|atliface.h \(également inclus dans ATLBase.h\)|  
  
## Voir aussi  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)