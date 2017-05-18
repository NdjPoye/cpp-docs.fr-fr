---
title: Interface de ICommandUI | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1db6b3fa58639140322816c37103566353b15633
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="icommandui-interface"></a>Interface de ICommandUI
Gère les commandes de l’interface utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[icommandui__Check](#check)|Définit l’élément d’interface utilisateur pour cette commande à l’état d’activation appropriée.|  
|[ICommandUI::ContinueRouting](#continuerouting)|Indique au mécanisme de routage des commandes pour continuer le routage du message en cours dans la chaîne de gestionnaires.|  
|[ICommandUI::Enabled](#enabled)|Active ou désactive l’élément d’interface utilisateur pour cette commande.|  
|[ICommandUI::ID](#id)|Obtient l’ID de l’objet d’interface utilisateur représenté par le `ICommandUI` objet.|  
|[ICommandUI::Index](#index)|Obtient l’index de l’objet d’interface utilisateur représenté par le `ICommandUI` objet.|  
|[ICommandUI::Radio](#radio)|Définit l’élément d’interface utilisateur pour cette commande à l’état d’activation appropriée.|  
|[ICommandUI::Text](#text)|Définit le texte de l’élément d’interface utilisateur pour cette commande.|  
  
## <a name="remarks"></a>Remarques  
 Cette interface fournit les méthodes et propriétés qui gèrent les commandes de l’interface utilisateur. `ICommandUI`est semblable à [CCmdUI (classe)](../../mfc/reference/ccmdui-class.md), sauf que `ICommandUI` est utilisé pour les applications MFC qui interagissent avec des composants .NET.  
  
 `ICommandUI`est utilisé dans un `ON_UPDATE_COMMAND_UI` gestionnaire dans un [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-classe dérivée. Lorsqu’un utilisateur d’une application active (Active ou clics) un menu, chaque élément de menu s’affiche comme activé ou désactivé. La cible de chaque commande de menu fournit ces informations en implémentant un `ON_UPDATE_COMMAND_UI` gestionnaire. Pour chacun des objets d’interface utilisateur commande dans votre application, utilisez la fenêtre Propriétés pour créer une entrée de table des messages et un prototype de fonction pour chaque gestionnaire.  
  
 Pour plus d’informations sur la façon dont les `ICommandUI` interface est utilisée dans le routage des commandes, consultez [Comment : ajouter routage des commandes au contrôle Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Pour plus d’informations sur la gestion des commandes de l’interface utilisateur dans les MFC, consultez [CCmdUI (classe)](../../mfc/reference/ccmdui-class.md).  
  
## <a name="check"></a>ICommandUI::Check  
Définit l’élément d’interface utilisateur pour cette commande à l’état d’activation appropriée.
```
property UICheckState Check;
```
## <a name="remarks"></a>Remarques  
Cette propriété définit l’élément d’interface utilisateur pour cette commande à l’état d’activation appropriée. Contrôle de la définition les valeurs suivantes :  
- Décochez&0;  
- 1 vérification  
- 2 Définissez indéterminé  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
Indique le mécanisme d’acheminement pour continuer le routage du message en cours dans la chaîne des gestionnaires de commandes.
```
void ContinueRouting();
```
## <a name="remarks"></a>Notes
Il s’agit d’une fonction membre avancée qui doit être utilisée conjointement avec un gestionnaire ON_COMMAND_EX qui renvoie la valeur FALSE. Pour plus d’informations, consultez Technical Note TN006 : tables des messages.

## <a name="enabled"></a>ICommandUI::Enabled 
Active ou désactive l’élément d’interface utilisateur pour cette commande.
```
property bool Enabled;
```
## <a name="remarks"></a>Remarques
Cette propriété Active ou désactive l’élément d’interface utilisateur pour cette commande. True pour activer l’élément, FALSE pour le désactiver, définissez Enabled (activé).

## <a name="id"></a>ICommandUI::ID  
Obtient l’ID de l’objet d’interface utilisateur représenté par l’objet ICommandUI.
```
property unsigned int ID;
```
## <a name="remarks"></a>Notes
Cette propriété obtient l’ID de l’élément de menu, bouton de barre d’outils ou un autre objet d’interface utilisateur représenté par l’objet ICommandUI (un handle).

## <a name="index"></a>ICommandUI::Index   
Obtient l’index de l’objet d’interface utilisateur représenté par l’objet ICommandUI.
```
property unsigned int Index;
```
## <a name="remarks"></a>Notes
Cette propriété obtient l’index de l’élément de menu, bouton de barre d’outils ou un autre objet d’interface utilisateur représenté par l’objet ICommandUI (un handle).

## <a name="radio"></a>ICommandUI::Radio 
Définit l’élément d’interface utilisateur pour cette commande à l’état d’activation appropriée.
```
property bool Radio;
```
## <a name="remarks"></a>Notes
Cette propriété définit l’élément d’interface utilisateur pour cette commande à l’état d’activation appropriée. Définir des cases d’option à True pour activer l’élément ; Sinon, FALSE.

## <a name="text"></a>ICommandUI::Text 
Définit le texte de l’élément d’interface utilisateur pour cette commande.
```
property String^ Text;
```
## <a name="remarks"></a>Notes
Cette propriété définit le texte de l’élément d’interface utilisateur pour cette commande. Définir le texte à un descripteur de chaîne de texte.

## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwinforms.h (défini dans l’assembly atlmfc\lib\mfcmifc80.dll)  
  
## <a name="see-also"></a>Voir aussi  
 [CCmdUI (classe)](../../mfc/reference/ccmdui-class.md)

