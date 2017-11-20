---
title: "ODBC : Configuration d’une Source de données ODBC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8e347683a079227226513ce82f9623860e826228
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-configuring-an-odbc-data-source"></a>ODBC : configuration d'une source de données ODBC
Pour utiliser un [source de données](../../data/odbc/data-source-odbc.md) avec une application que vous avez développés, vous devez utiliser l’administrateur ODBC pour la configurer. L’administrateur ODBC assure le suivi des sources de données disponibles et leurs informations de connexion dans le Registre Windows. Utilisez l’administrateur ODBC pour ajouter, modifier et supprimer des sources de données dans le **des Sources de données** boîte de dialogue et d’ajouter et supprimer des pilotes ODBC.  
  
> [!NOTE]
>  Ces informations s’appliquent lorsque vous utilisez les classes de données Access objet DAO (MFC) pour accéder à ODBC et lorsque vous utilisez les classes ODBC MFC.  
  
 Administrateur ODBC est automatiquement installé avec la prise en charge de la base de données de la bibliothèque Microsoft Foundation Classes (MFC). Pour plus d’informations sur le programme Administrateur ODBC, consultez [administrateur ODBC](../../data/odbc/odbc-administrator.md) et le système d’aide ODBC API Reference en ligne.  
  
 Pour plus d’informations sur la façon d’écrire des programmes d’installation ODBC et d’Administration pour les applications de base de données MFC,[Technical Note 48](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Principes de base ODBC](../../data/odbc/odbc-basics.md)   
 [ODBC : appel direct de fonctions API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)