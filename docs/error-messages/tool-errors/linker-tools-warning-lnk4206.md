---
title: "LNK4206 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.date: 12/05/2017
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4206
dev_langs:
- C++
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd13ac59aefa074db869f0502743c7a49d23082c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4206"></a>Avertissement des outils Éditeur de liens LNK4206

> informations de type précompilé non trouvées ; '*nom de fichier*' non lié ou remplacé ; objet sera lié sans informations de débogage

Le *nom de fichier* fichier objet compilé à l’aide de [/Yc](../../build/reference/yc-create-precompiled-header-file.md), était soit non spécifié dans la commande LINK ou a été remplacé.

Un scénario courant pour cet avertissement est lorsque le fichier .obj qui a été compilé avec /Yc se trouve dans une bibliothèque, et où il n’existe aucune référence de symbole à ce fichier .obj à partir de votre code.  Dans ce cas, l’éditeur de liens ne sera pas utiliser (ou même voir) le fichier .obj.  Dans ce cas, vous devez recompiler votre code et utiliser [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) pour les objets compilés à l’aide de [/Yu](../../build/reference/yu-use-precompiled-header-file.md).