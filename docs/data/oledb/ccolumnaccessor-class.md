---
title: Ccolumnaccessor, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs: C++
helpviewer_keywords: CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55c77a53cb6e6c4a103c509aa3d527803d91af3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor, classe
Génère le code de consommateur injecté.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Notes  
 Dans le code injecté, chaque colonne est liée en tant qu’un accesseur séparé. Vous devez être conscient que cette classe est utilisée dans le code injecté (par exemple, vous pouvez rencontrer il lors du débogage), mais vous devez en général jamais directement l’utiliser ou ses méthodes.  
  
 `CColumnAccessor`implémente les méthodes stub suivantes, chacune d’elles correspondant de fonctionnalités à d’autres méthodes d’accesseur de classe :  
  
-   `CColumnAccessor`Le constructeur ; instancie et initialise le `CColumnAccessor` objet.  
  
-   `CreateAccessor`Alloue de la mémoire pour la colonne de structures de liaison et initialise les membres de données de colonne.  
  
-   **BindColumns** lie les colonnes aux accesseurs.  
  
-   **SetParameterBuffer** alloue des mémoires tampons pour les paramètres.  
  
-   `AddParameter`Ajoute une entrée de paramètre pour les structures d’entrée de paramètre.  
  
-   **HasOutputColumns** détermine si l’accesseur a des colonnes de sortie  
  
-   **HasParameters** détermine si l’accesseur a des paramètres.  
  
-   `BindParameters`Lie les paramètres aux colonnes.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)