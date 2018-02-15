---
title: QueryInterface | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce14ebef3649cea78e8cf4315a62392cfa142152
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="queryinterface"></a>QueryInterface
Bien qu’il existe des mécanismes par lequel un objet peut exprimer la fonctionnalité qu’elle fournit statiquement (avant son instanciation), le mécanisme COM de base consiste à utiliser le **IUnknown** méthode appelée [QueryInterface ](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Chaque interface est dérivée de **IUnknown**, de sorte que chaque interface a une implémentation de `QueryInterface`. Quelle que soit l’implémentation, cette méthode interroge un objet à l’aide de l’IID de l’interface à laquelle l’appelant veut un pointeur. Si l’objet prend en charge cette interface, `QueryInterface` récupère un pointeur vers l’interface, tout en appelant `AddRef`. Sinon, elle retourne le **E_NOINTERFACE** code d’erreur.  
  
 Notez que vous devez respecter [décompte](../atl/reference-counting.md) règles à tout moment. Si vous appelez **version** sur un pointeur d’interface pour décrémenter le décompte de références à zéro, n’utilisez pas ce pointeur à nouveau. Parfois, vous devrez peut-être obtenir une référence faible à un objet (autrement dit, vous pouvez souhaiter obtenir un pointeur vers une de ses interfaces sans incrémenter le décompte de références), mais il n’est pas acceptable pour ce faire, appelez `QueryInterface` suivie  **Version**. Le pointeur obtenu de la sorte n’est pas valide et ne doit pas être utilisé. Cela plus facilement devient évidente lorsque [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) est définie, la définition de cette macro est un moyen pratique de bogues de comptage de références de recherche.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à COM](../atl/introduction-to-com.md)   
 [QueryInterface : Navigation dans un objet](http://msdn.microsoft.com/library/windows/desktop/ms687230)

