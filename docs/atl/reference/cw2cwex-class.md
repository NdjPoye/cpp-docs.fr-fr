---
title: Classe de CW2CWEX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
caps.latest.revision: 20
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 5dca6b31cdd99582e727b634093c3548eef2ecc1
ms.contentlocale: fr-fr
ms.lasthandoff: 03/31/2017

---
# <a name="cw2cwex-class"></a>Classe de CW2CWEX
Cette classe est utilisée par les macros de conversion de chaînes `CW2CTEX` et `CT2CWEX`et le typedef `CW2W`.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction. La longueur par défaut est 128 octets.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|Constructeur.|  
|[CW2CWEX :: ~ CW2CWEX](#dtor)|Destructeur.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|Opérateur de conversion.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|Le membre de données qui stocke la chaîne source.|  
  
## <a name="remarks"></a>Remarques  
 À moins que des fonctionnalités supplémentaires sont requises, utilisez `CW2CTEX`, `CT2CWEX`, ou `CW2W` dans votre code.  
  
 Cette classe est plus sûr d’utiliser dans les boucles et ne sera pas dépassement de la pile. Par défaut, les macros et les classes de conversion ATL utilisent page de codes ANSI du thread actuel pour la conversion.  
  
 Les macros suivantes sont basées sur cette classe :  
  
- `CW2CTEX`  
  
- `CT2CWEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
- `CW2W`  
  
 Pour en savoir plus sur ces macros de conversion de texte, consultez [ATL et MFC Macros de Conversion de chaînes](string-conversion-macros.md).  
  
## <a name="example"></a>Exemple  
 Consultez [ATL et MFC Macros de Conversion de chaînes](string-conversion-macros.md) pour obtenir un exemple d’utilisation de ces macros de conversion de chaînes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlconv.h  
  
##  <a name="cw2cwex"></a>CW2CWEX::CW2CWEX  
 Constructeur.  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne de texte à convertir.  
  
 `nCodePage`  
 La page de codes. Pas utilisé dans cette classe.  
  
### <a name="remarks"></a>Notes  
 Alloue de la mémoire tampon utilisée dans le processus de traduction.  
  
##  <a name="dtor"></a>CW2CWEX :: ~ CW2CWEX  
 Destructeur.  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>Notes  
 Libère la mémoire tampon allouée.  
  
##  <a name="m_psz"></a>CW2CWEX::m_psz  
 Le membre de données qui stocke la chaîne source.  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="operator_lpcwstr"></a>CW2CWEX::operator LPCWSTR  
 Opérateur de conversion.  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la chaîne de texte en tant que type **LPCWSTR.**  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Classe de CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Classe de CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Classe de CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Classe de CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
