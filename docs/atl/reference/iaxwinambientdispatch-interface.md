---
title: "IAxWinAmbientDispatch Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinAmbientDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatch interface"
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# IAxWinAmbientDispatch Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette interface fournit des méthodes pour spécifier des caractéristiques du contrôle ou du conteneur hébergé.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
interface IAxWinAmbientDispatch : IDispatch  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[get\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::get_AllowContextMenu.md)|La propriété d' **AllowContextMenu** spécifie si est autorisé à le contrôle hébergé pour afficher son propre menu contextuel.|  
|[get\_AllowShowUI](../Topic/IAxWinAmbientDispatch::get_AllowShowUI.md)|La propriété d' **AllowShowUI** spécifie si est autorisé à le contrôle hébergé pour examiner leur propre interface utilisateur.|  
|[get\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::get_AllowWindowlessActivation.md)|La propriété d' **AllowWindowlessActivation** spécifie si le conteneur permet l'activation sans fenêtre.|  
|[get\_BackColor](../Topic/IAxWinAmbientDispatch::get_BackColor.md)|La propriété d' `BackColor` spécifie la couleur d'arrière\-plan ambiante du conteneur.|  
|[get\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::get_DisplayAsDefault.md)|**DisplayAsDefault** est une propriété ambiante qui permet à un contrôle pour déterminer si c'est le contrôle par défaut.|  
|[get\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::get_DocHostDoubleClickFlags.md)|La propriété de **DocHostDoubleClickFlags** spécifie l'opération que doit avoir lieu en réponse à un double\-clic.|  
|[get\_DocHostFlags](../Topic/IAxWinAmbientDispatch::get_DocHostFlags.md)|La propriété de **DocHostFlags** spécifie les fonctions d'interface utilisateur de l'objet hôte.|  
|[get\_Font](../Topic/IAxWinAmbientDispatch::get_Font.md)|La propriété de **Police** spécifie la police ambiante du conteneur.|  
|[get\_ForeColor](../Topic/IAxWinAmbientDispatch::get_ForeColor.md)|La propriété d' `ForeColor` spécifie la couleur de premier plan ambiante du conteneur.|  
|[get\_LocaleID](../Topic/IAxWinAmbientDispatch::get_LocaleID.md)|La propriété de **LocaleID** spécifie l'ID de paramètres régionaux ambiant du conteneur.|  
|[get\_MessageReflect](../Topic/IAxWinAmbientDispatch::get_MessageReflect.md)|La propriété ambiante de **MessageReflect** spécifie si le conteneur reflétera des messages au contrôle hébergé.|  
|[get\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::get_OptionKeyPath.md)|La propriété d' **OptionKeyPath** spécifie le chemin d'accès de clé de Registre aux paramètres utilisateur.|  
|[get\_ShowGrabHandles](../Topic/IAxWinAmbientDispatch::get_ShowGrabHandles.md)|La propriété ambiante de **ShowGrabHandles** permet au contrôle afin de déterminer si elle se dessine avec des poignées de manipulation.|  
|[get\_ShowHatching](../Topic/IAxWinAmbientDispatch::get_ShowHatching.md)|La propriété ambiante de **ShowHatching** permet au contrôle afin de déterminer si elle se dessine hachait.|  
|[get\_UserMode](../Topic/IAxWinAmbientDispatch::get_UserMode.md)|La propriété d' **UserMode** spécifie le mode ambiant utilisateur du conteneur.|  
|[put\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::put_AllowContextMenu.md)|La propriété d' **AllowContextMenu** spécifie si est autorisé à le contrôle hébergé pour afficher son propre menu contextuel.|  
|[put\_AllowShowUI](../Topic/IAxWinAmbientDispatch::put_AllowShowUI.md)|La propriété d' **AllowShowUI** spécifie si est autorisé à le contrôle hébergé pour examiner leur propre interface utilisateur.|  
|[put\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::put_AllowWindowlessActivation.md)|La propriété d' **AllowWindowlessActivation** spécifie si le conteneur permet l'activation sans fenêtre.|  
|[put\_BackColor](../Topic/IAxWinAmbientDispatch::put_BackColor.md)|La propriété d' `BackColor` spécifie la couleur d'arrière\-plan ambiante du conteneur.|  
|[put\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::put_DisplayAsDefault.md)|**DisplayAsDefault** est une propriété ambiante qui permet à un contrôle pour déterminer si c'est le contrôle par défaut.|  
|[put\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::put_DocHostDoubleClickFlags.md)|La propriété de **DocHostDoubleClickFlags** spécifie l'opération que doit avoir lieu en réponse à un double\-clic.|  
|[put\_DocHostFlags](../Topic/IAxWinAmbientDispatch::put_DocHostFlags.md)|La propriété de **DocHostFlags** spécifie les fonctions d'interface utilisateur de l'objet hôte.|  
|[put\_Font](../Topic/IAxWinAmbientDispatch::put_Font.md)|La propriété de **Police** spécifie la police ambiante du conteneur.|  
|[put\_ForeColor](../Topic/IAxWinAmbientDispatch::put_ForeColor.md)|La propriété d' `ForeColor` spécifie la couleur de premier plan ambiante du conteneur.|  
|[put\_LocaleID](../Topic/IAxWinAmbientDispatch::put_LocaleID.md)|La propriété de **LocaleID** spécifie l'ID de paramètres régionaux ambiant du conteneur.|  
|[put\_MessageReflect](../Topic/IAxWinAmbientDispatch::put_MessageReflect.md)|La propriété ambiante de **MessageReflect** spécifie si le conteneur reflétera des messages au contrôle hébergé.|  
|[put\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::put_OptionKeyPath.md)|La propriété d' **OptionKeyPath** spécifie le chemin d'accès de clé de Registre aux paramètres utilisateur.|  
|[put\_UserMode](../Topic/IAxWinAmbientDispatch::put_UserMode.md)|La propriété d' **UserMode** spécifie le mode ambiant utilisateur du conteneur.|  
  
## Notes  
 Cette interface est exposée par le contrôle ActiveX ATL hébergement d'objets.  Appelez les méthodes sur cette interface pour définir les propriétés ambiantes disponibles pour le contrôle hébergé ou pour spécifier d'autres aspects du comportement du conteneur.  Pour remplir les propriétés fournies par `IAxWinAmbientDispatch`, utilisez [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) essaiera de charger les informations de type à propos de `IAxWinAmbientDispatch` et d' `IAxWinAmbientDispatchEx` le typelib qui contient le code.  
  
 Si vous liez à ATL90.dll, **AXHost** charge des informations de type du typelib dans la DLL.  
  
 Consultez [Contrôles ActiveX d'hébergement à l'aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour plus de détails.  
  
## Configuration requise  
 La définition de cette interface est disponible sous plusieurs formes, comme indiqué dans le tableau ci\-dessous.  
  
|Type de définition|Fichier|  
|------------------------|-------------|  
|IDL|atliface.idl|  
|Bibliothèque de types|ATL.dll|  
|C\+\+|atliface.h \(également inclus dans ATLBase.h\)|  
  
## Voir aussi  
 [IAxWinAmbientDispatchEx Interface](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow Interface](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)