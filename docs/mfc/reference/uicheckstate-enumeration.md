---
title: "Énumération UICheckState | Documents Microsoft"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxwinforms/uicheckstate
dev_langs:
- C++
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 21b23efdbad9f2b867b104d0a0d9d0bbb4338e5a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---

# <a name="uicheckstate-enumeration"></a>Énumération UICheckState
Décrit l’état d’activation d’un élément d’interface utilisateur pour la commande.  
   
### <a name="syntax"></a>Syntaxe   
```  
public enum class 
{  
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]  
   Unchecked,   
   Checked,   
   Indeterminate 
};  
```  
   
### <a name="remarks"></a>Remarques  
 [ICommandUI::Check](icommandui-interface.md#check) utilise ces valeurs pour décrire l’état d’un élément d’interface utilisateur.    
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle d’utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Spécifications  
 **En-tête :** afxwinforms.h (défini dans l’assembly atlmfc\lib\mfcmifc80.dll)  

