---
title: Hse_version_info, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 78b1ed79093db179e00f262b61934ff9c293ff18
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO, structure
Cette structure est pointée par le `pVer` paramètre dans le `CHttpServer::GetExtensionVersion` fonction membre. Il fournit le numéro de version ISA et une description de l’ISA.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *dwExtensionVersion*  
 Le numéro de version de l’ISA.  
  
 *lpszExtensionDesc*  
 La description de l’ISA. L’implémentation par défaut fournit le texte d’espace réservé ; substituer `CHttpServer::GetExtensionVersion` afin de fournir votre propre description.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** httpext.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


