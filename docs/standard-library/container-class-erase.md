---
title: Conteneur Class::erase | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5a817ed259f5bd264d82fc948afa4cdcd70be2e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="container-classerase"></a>Conteneur Class::erase

> [!NOTE]
> Cette rubrique fait partie de la documentation Visual C++ comme exemple non fonctionnel de conteneurs utilisés dans la bibliothèque standard C++. Pour plus d’informations, consultez [Conteneurs de la bibliothèque standard C++](../standard-library/stl-containers.md).

Efface un élément.

## <a name="syntax"></a>Syntaxe

```

    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Notes

La première fonction membre supprime l’élément de la séquence contrôlée vers lequel pointé *_Where*. La deuxième fonction membre supprime l’élément de la séquence contrôlée dans la plage [`first`, `last`). Les deux fonctions retournent un itérateur qui désigne le premier élément restant après tous les éléments supprimés, ou [end](../standard-library/container-class-end.md) si aucun élément de ce genre n’existe.

Les fonctions membres lèvent une exception uniquement si une opération de copie lève une exception.

## <a name="see-also"></a>Voir aussi

[Sample Container, classe](../standard-library/sample-container-class.md)<br/>
