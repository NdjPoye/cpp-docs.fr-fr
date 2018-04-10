---
title: Listes d’initialiseurs | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- initializer lists
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1af020bec295f0f949b7ebb6abe88102f3942b1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="initializer-lists"></a>Listes d'initialiseurs
Listes d’initialiseurs de constructeurs sont maintenant appelées avant le constructeur de classe de base.  
  
## <a name="remarks"></a>Notes  
 Avant Visual C++ 2005, le constructeur de classe de base a été appelé avant la liste d’initialiseurs lors de la compilation avec les Extensions managées pour C++. Désormais, lors de la compilation avec **/CLR**, la liste d’initialiseurs est appelée en premier.  
  
## <a name="see-also"></a>Voir aussi  
 [Modifications d’ordre général apportées au langage (C++-CLI)](../dotnet/general-language-changes-cpp-cli.md)