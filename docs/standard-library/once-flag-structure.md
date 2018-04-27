---
title: once_flag, structure | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 249207d8723318c1a11760c512f3b88f13c97266
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="onceflag-structure"></a>once_flag, structure

Représente un `struct` utilisé avec la fonction de modèle [call_once](../standard-library/mutex-functions.md#call_once) pour garantir que le code d’initialisation est appelé une seule fois, même en présence de plusieurs threads d’exécution.

## <a name="syntax"></a>Syntaxe

struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };

## <a name="remarks"></a>Notes

Le `once_flag` `struct` possède uniquement un constructeur par défaut.

Les objets de type `once_flag` peuvent être créés, mais ils ne peuvent pas être copiés.

## <a name="requirements"></a>Spécifications

**En-tête :** \<mutex >

**Espace de noms :** std

## <a name="see-also"></a>Voir aussi

[Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
