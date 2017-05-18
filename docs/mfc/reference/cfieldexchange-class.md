---
title: Classe de CFieldExchange | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs:
- C++
helpviewer_keywords:
- enum FieldType, CFieldExchange
- RFX (record field exchange) [C++]
- RFX (record field exchange) [C++], classes for
- CFieldExchange class
- FieldType enumeration
- data types [C++], custom
- enum FieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 948f13dc54fcd83941bab8e63b2ab2704d84cb87
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cfieldexchange-class"></a>CFieldExchange (classe)
Prend en charge les routines d'échange de champs d'enregistrements (RFX) et d'échange de champs d'enregistrements en bloc (RFX en bloc) utilisées par les classes de base de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|Retourne zéro si l’opération en cours est approprié pour le type du champ mis à jour.|  
|[CFieldExchange::SetFieldType](#setfieldtype)|Spécifie le type de membre de données de jeu d’enregistrements : colonne ou paramètre — représenté par tous les appels suivants à RFX (fonctions) jusqu'à ce que l’appel suivant à `SetFieldType`.|  
  
## <a name="remarks"></a>Notes  
 `CFieldExchange`n’a pas d’une classe de base.  
  
 Utilisez cette classe si vous écrivez des routines d’échange de données pour les types de données personnalisés ou lorsque vous implémentez l’extraction de lignes en bloc ; Sinon, vous pas directement utilisera cette classe. RFX et RFX en bloc échange des données entre les membres de données de champ de votre objet recordset et les champs correspondants de l’enregistrement actif dans la source de données.  
  
> [!NOTE]
>  Si vous travaillez avec les classes d’objets d’accès aux données (DAO) plutôt que les classes Open Database Connectivity (ODBC), utilisez la classe [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) à la place. Pour plus d’informations, consultez l’article [vue d’ensemble : base de données de programmation](../../data/data-access-programming-mfc-atl.md).  
  
 Un `CFieldExchange` objet fournit les informations de contexte nécessitaient pour RFX ou RFX en bloc se placer. `CFieldExchange`objets prennent en charge un nombre d’opérations, y compris les paramètres de liaison et les données membres de champ et le paramètre différents indicateurs sur les champs de l’enregistrement actif. RFX et RFX en bloc des opérations sont effectuées sur les membres de données de classe de jeu d’enregistrements de types définis par le `enum` **FieldType** dans `CFieldExchange`. Possible **FieldType** les valeurs sont :  
  
- **CFieldExchange::outputColumn** pour les membres de données de champ.  
  
- **CFieldExchange::inputParam** ou **CFieldExchange::param** pour les membres de données de paramètre d’entrée.  
  
- **CFieldExchange::outputParam** des membres de données de paramètre de sortie.  
  
- **CFieldExchange::inoutParam** pour les membres de données de paramètre d’entrée/sortie.  
  
 La plupart des membres de données et des fonctions de membre de la classe est fournie pour l’écriture de vos propres routines RFX personnalisés. Vous allez utiliser `SetFieldType` fréquemment. Pour plus d’informations, consultez les articles [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md) et [Recordset (ODBC)](../../data/odbc/recordset-odbc.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Pour plus d’informations sur les fonctions globales RFX et RFX en bloc, consultez [fonctions Record Field Exchange](../../mfc/reference/record-field-exchange-functions.md) dans la section MFC Macros and Globals de cette référence.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CFieldExchange`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdb.h  
  
##  <a name="isfieldtype"></a>CFieldExchange::IsFieldType  
 Si vous écrivez votre propre fonction RFX, appelez `IsFieldType` au début de votre fonction pour déterminer si l’opération en cours peut être exécutée sur un type de membre données champ ou un paramètre particulier (une **CFieldExchange::outputColumn**, **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, ou **CFieldExchange::inoutParam**).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>Paramètres  
 *pnField*  
 Numéro séquentiel de la donnée membre de champ ou un paramètre est retourné dans ce paramètre. Cette valeur correspond à l’ordre du membre de données dans le [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) ou [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) (fonction).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération en cours peut être effectuée sur le type de champ ou le paramètre actuel.  
  
### <a name="remarks"></a>Remarques  
 Suivre le modèle des fonctions RFX existants.  
  
##  <a name="setfieldtype"></a>CFieldExchange::SetFieldType  
 Vous avez besoin d’un appel à `SetFieldType` dans votre classe de recordset [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) ou [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) remplacer.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Paramètres  
 `nFieldType`  
 Une valeur de la **enum FieldType**, déclarés dans `CFieldExchange`, qui peut être une des opérations suivantes :  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>Remarques  
 Pour les membres de données de champ, vous devez appeler `SetFieldType` avec un paramètre de **CFieldExchange::outputColumn**, suivi par des appels aux fonctions RFX ou RFX en bloc. Si vous n’avez pas implémenté l’extraction de lignes en bloc, puis place ClassWizard `SetFieldType` appeler pour vous dans la section de mappage de champs de `DoFieldExchange`.  
  
 Si vous paramétrez votre classe de recordset, vous devez appeler `SetFieldType` à nouveau, en dehors d’une section de mappage de champ, suivi d’appels RFX pour tous les membres de données de paramètre. Chaque type de membre de données de paramètre doit avoir son propre `SetFieldType` appeler. Le tableau suivant fait la distinction les différentes valeurs que vous pouvez passer à `SetFieldType` pour représenter les membres de données de paramètre de la classe :  
  
|Valeur du paramètre SetFieldType|Type de membre de données de paramètre|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|Paramètre d’entrée. Une valeur qui est passée dans la requête ou la procédure stockée du jeu d’enregistrements.|  
|**CFieldExchange::param**|Identique à **CFieldExchange::inputParam**.|  
|**CFieldExchange::outputParam**|Paramètre de sortie. Une valeur de retour de procédure stockée du jeu d’enregistrements.|  
|**CFieldExchange::inoutParam**|Paramètre d’entrée/sortie. Une valeur qui est passée et retournée à partir de la procédure stockée du jeu d’enregistrements.|  
  
 En général, chaque groupe d’appels de fonction RFX associé aux données membres de champ ou de membres de données de paramètre doit être précédé par un appel à `SetFieldType`. Le `nFieldType` paramètre de chaque `SetFieldType` appel identifie le type des membres de données représenté par les appels de fonction RFX qui suivent le `SetFieldType` appeler.  
  
 Pour plus d’informations sur la gestion des paramètres de sortie et d’entrée/sortie, consultez le `CRecordset` fonction membre [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). Pour plus d’informations sur les fonctions RFX et RFX en bloc, consultez la rubrique [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Exemple  
 Cet exemple illustre plusieurs appels de fonctions RFX en termes d’appels à `SetFieldType`. Notez que `SetFieldType` est appelé via le `pFX` pointeur vers un `CFieldExchange` objet.  
  
 [!code-cpp[NVC_MFCDatabase&#33;](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRecordset (classe)](../../mfc/reference/crecordset-class.md)

