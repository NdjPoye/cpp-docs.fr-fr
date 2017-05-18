---
title: Interface de ICommandTarget | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs:
- C++
helpviewer_keywords:
- ICommandTarget interface
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 825fde18c56afb91bdb469212817109dc35abf68
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="icommandtarget-interface"></a>Interface de ICommandTarget
Fournit un contrôle utilisateur avec une interface de recevoir des commandes à partir d’un objet de source de commande.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ICommandTarget::Initialize](#initialize)|Initialise l’objet cible de commande.|  
  
## <a name="remarks"></a>Remarques  
 Lorsque vous hébergez un contrôle utilisateur dans une vue de MFC, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) commandes d’itinéraires et de mise à jour de commande des messages de l’interface utilisateur pour le contrôle utilisateur pour lui permettre de gérer les commandes MFC (par exemple, les éléments de menu de frame et boutons de barre d’outils). En implémentant `ICommandTarget`, vous donnez le contrôle, une référence à la [ICommandSource](../../mfc/reference/icommandsource-interface.md) objet.  
  
 Consultez la page [Comment : ajouter routage des commandes au contrôle Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) pour obtenir un exemple montrant comment utiliser `ICommandTarget`.  
  
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwinforms.h (défini dans l’assembly atlmfc\lib\mfcmifc80.dll)  
  
##  <a name="initialize"></a>ICommandTarget::Initialize  
 Initialise l’objet cible de commande.  
  
```  
void Initialize(ICommandSource^ cmdSource);  
```  
  
### <a name="parameters"></a>Paramètres  
 `cmdSource`  
 Handle vers l’objet de source de commande.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous hébergez un contrôle utilisateur dans une vue de MFC, CWinFormsView route les commandes et les messages de l’interface utilisateur de commande de mise à jour pour le contrôle utilisateur pour lui permettre de gérer les commandes MFC.  
  
 Cette méthode initialise l’objet cible de commande et l’associe à la cmdSource d’objet de source de commande spécifiée. Elle doit être appelée dans l’implémentation de classe de contrôle utilisateur. Lors de l’initialisation, vous devez inscrire des gestionnaires de commandes avec l’objet de source de commande en appelant ICommandSource::AddCommandHandler dans l’implémentation de l’initialisation. Consultez Comment : ajouter le routage des commandes au contrôle Windows Forms pour obtenir un exemple d’utilisation d’initialisation pour ce faire.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : ajouter des commandes routage pour les Windows Forms contrôle](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [Interface de ICommandSource](../../mfc/reference/icommandsource-interface.md)




