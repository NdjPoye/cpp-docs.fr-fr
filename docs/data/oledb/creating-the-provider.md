---
title: "Création du fournisseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6e590461d359c2ab2ee750f0393f6c2f9ec7ac95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-provider"></a>Création du fournisseur
#### <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>Pour créer un fournisseur OLE DB avec l’Assistant fournisseur OLE DB ATL  
  
1.  Cliquez sur le projet.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **ajouter une classe**.  
  
3.  Dans le **ajouter une classe** boîte de dialogue, sélectionnez le **fournisseur OLE DB ATL** icône, puis cliquez sur **ouvrir**.  
  
4.  Dans l’Assistant fournisseur OLE DB ATL, entrez un nom court pour le fournisseur dans le **nom court** boîte. Les rubriques suivantes utilisent le nom court « MyProvider », mais vous pouvez utiliser un autre nom. Les autres zones de nom remplissent en fonction du nom que vous entrez.  
  
5.  Modifiez les autres zones de nom si nécessaire. Outre les noms d’objet et de fichier, vous pouvez modifier les éléments suivants :  
  
    -   **Coclasse**: le nom utilisé par COM pour créer le fournisseur.  
  
    -   **ProgID**: l’identificateur programmatique, qui est une chaîne de texte qui peut être utilisée à la place d’un GUID.  
  
    -   **Version**: utilisée avec ProgID et coclasse pour générer un ID programmatique de dépendants de la version.  
  
6.  Cliquez sur **Terminer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)