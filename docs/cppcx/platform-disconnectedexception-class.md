---
title: Platform::disconnectedexception, classe | Documents Microsoft
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
dev_langs: C++
helpviewer_keywords: Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9ce20c019c022ed62c2be888617b387315731b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="platformdisconnectedexception-class"></a>Platform::DisconnectedException, classe
Levée quand un objet proxy COM essaie de faire référence à un serveur COM qui n'existe plus  
  
## <a name="syntax"></a>Syntaxe  
  
```  
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Notes  
 Quand une classe A fait référence à une autre classe (classe B) qui se trouve dans un processus séparé, la classe A nécessite un objet proxy pour communiquer avec le serveur COM hors processus qui contient la classe B. Parfois, le serveur peut ne plus avoir suffisamment de mémoire, sans que la classe A ne s’en aperçoive. Dans ce cas, l'exception RPC_E_DISCONNECTED est levée et est traduite en Platform::DisconnectedException. Cela peut se produire dans un scénario dans lequel une source d'événement appelle un délégué qui lui a été passé, mais que le délégué a été supprimé une fois abonné à l'événement. Lorsque cela se produit, la source d'événement supprime ce délégué de sa liste d'appels.  
  
 Pour plus d'informations, consultez la classe [COMException](../cppcx/platform-comexception-class.md) .  
  
### <a name="requirements"></a>Configuration requise  
 **Minimum pris en charge le client :** Windows 8  
  
 **Minimum de serveur pris en charge :** Windows Server 2012  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## <a name="see-also"></a>Voir aussi  
 [Platform::COMException, classe](../cppcx/platform-comexception-class.md)