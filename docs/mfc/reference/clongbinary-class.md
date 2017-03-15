---
title: CLongBinary (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BLOB
- CLongBinary
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object)
- CLongBinary class
- BLOB (binary large object), CLongBinary class
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bb73604ee4d15f3a71be8514f348ad265064928a
ms.lasthandoff: 02/24/2017

---
# <a name="clongbinary-class"></a>CLongBinary (classe)
Simplifie l'utilisation d'objets de données binaires de très grande taille (souvent appelés BLOB ou « objets blob ») dans une base de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|Construit un objet `CLongBinary`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Contient la taille réelle en octets de l’objet de données dont le handle est stocké dans `m_hData`.|  
|[CLongBinary::m_hData](#m_hdata)|Contient un Windows `HGLOBAL` handle de l’objet de l’image réelle.|  
  
## <a name="remarks"></a>Notes  
 Par exemple, un champ d’enregistrement dans une table SQL peut contenir une image bitmap représentant une image. Un `CLongBinary` objet stocke ce type d’objet et effectue le suivi de sa taille.  
  
> [!NOTE]
>  En général, il est maintenant de meilleure pratique d’utiliser [CByteArray](../../mfc/reference/cbytearray-class.md) conjointement avec la [DFX_Binary](http://msdn.microsoft.com/library/678021a3-2e46-44d7-8528-71bb692dcc07) (fonction). Vous pouvez toujours utiliser `CLongBinary`, mais en général `CByteArray` fournit davantage de fonctionnalités sous Win32, car il n’est plus la limite de taille rencontrée avec 16 bits `CByteArray`. Ce Conseil s’applique à la programmation avec des objets d’accès aux données (DAO), ainsi que Open Database Connectivity (ODBC).  
  
 Pour utiliser un `CLongBinary` objet, déclarez un membre de données de champ de type `CLongBinary` dans votre classe de recordset. Ce membre est un membre de la classe de recordset incorporé et sera construit lors de la construction de l’objet recordset. Après le `CLongBinary` objet est construit, le mécanisme record field exchange (RFX) charge de l’objet de données à partir d’un champ dans l’enregistrement actif dans la source de données et la stocke à l’enregistrement lorsque l’enregistrement est mis à jour. RFX interroge la source de données pour la taille de l’objet BLOB, pour qu’il alloue le stockage (via la `CLongBinary` l’objet `m_hData` membre de données) et stocke un `HGLOBAL` handle vers les données de `m_hData`. RFX stocke également la taille réelle de l’objet de données dans le `m_dwDataLength` membre de données. Travailler avec les données de l’objet via `m_hData`, utilisant les mêmes techniques que vous utiliseriez normalement pour manipuler les données stockées dans un Windows `HGLOBAL` gérer.  
  
 Lorsque vous détruisez le jeu d’enregistrements, les données incorporée `CLongBinary` également détruit et le destructeur libère le `HGLOBAL` données descripteur.  
  
 Pour plus d’informations sur les objets de grande taille et l’utilisation de `CLongBinary`, consultez les articles [Recordset (ODBC)](../../data/odbc/recordset-odbc.md) et [Recordset : utilisation avec les éléments de données volumineux (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdb_.h  
  
##  <a name="a-nameclongbinarya--clongbinaryclongbinary"></a><a name="clongbinary"></a>CLongBinary::CLongBinary  
 Construit un objet `CLongBinary`.  
  
```  
CLongBinary();
```  
  
##  <a name="a-namemdwdatalengtha--clongbinarymdwdatalength"></a><a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength  
 Stocke la taille réelle en octets des données stockées dans les `HGLOBAL` gérer dans `m_hData`.  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>Notes  
 Cette taille peut être inférieure à la taille du bloc de mémoire alloué pour les données. Appelez Win32 [GLobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593) fonction permettant d’obtenir la taille allouée.  
  
##  <a name="a-namemhdataa--clongbinarymhdata"></a><a name="m_hdata"></a>CLongBinary::m_hData  
 Stocke un Windows `HGLOBAL` handle vers les données d’objet BLOB réel.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRecordset (classe)](../../mfc/reference/crecordset-class.md)

