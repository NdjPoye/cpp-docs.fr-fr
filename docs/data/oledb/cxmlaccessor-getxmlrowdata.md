---
title: CXMLAccessor::GetXMLRowData | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs: C++
helpviewer_keywords: GetXMLRowData method
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b21e48439fbf4f420751e2f89903044626df9c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cxmlaccessorgetxmlrowdata"></a>CXMLAccessor::GetXMLRowData
Récupère le contenu entier d’une table en tant que données de chaîne au format XML, par ligne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetXMLRowData(   
   CSimpleStringW& strOutput,   
   bool bAppend = false    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `strOutput`  
 [out] Une référence à une mémoire tampon contenant les données de table doit être récupéré. Les données sont formatées sous forme de données de chaîne avec des noms de balise XML qui correspondent aux noms de colonne du magasin de données.  
  
 *bAppend*  
 [in] Valeur booléenne spécifiant s’il faut ajouter une chaîne à la fin des données de sortie.  
  
## <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
## <a name="remarks"></a>Remarques  
 L’exemple suivant montre comment les données de ligne sont au format XML. `DATA`ci-dessous représente les données de ligne. Utilisez les méthodes pour passer à la ligne souhaitée de déplacement.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CXMLAccessor, classe](../../data/oledb/cxmlaccessor-class.md)