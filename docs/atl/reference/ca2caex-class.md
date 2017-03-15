---
title: Classe de CA2CAEX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CA2CAEX
- ATL.CA2CAEX<t_nBufferLength>
- ATLCONV/CA2CAEX
- ATL::CA2CAEX<t_nBufferLength>
- ATL::CA2CAEX
- CA2CAEX
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f104a62144e7fd8ac802c27dfe940a7f96d0e79a
ms.lasthandoff: 02/24/2017

---
# <a name="ca2caex-class"></a>CA2CAEX (classe)
Cette classe est utilisée par les macros de conversion de chaînes `CA2CTEX` et `CT2CAEX`et le typedef **CA2CA**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction. La longueur par défaut est 128 octets.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|Constructeur.|  
|[CA2CAEX :: ~ CA2CAEX](#dtor)|Destructeur.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|Opérateur de conversion.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|Le membre de données qui stocke la chaîne source.|  
  
## <a name="remarks"></a>Remarques  
 À moins que des fonctionnalités supplémentaires sont requises, utilisez `CA2CTEX`, `CT2CAEX`, ou **CA2CA** dans votre propre code.  
  
 Cette classe est sûr à utiliser dans des boucles et ne sont pas un dépassement de la pile. Par défaut, les classes et macros de conversion ATL utilisent la page de codes ANSI du thread actif pour la conversion.  
  
 Les macros suivantes sont basées sur cette classe :  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
- **CA2CA**  
  
 Pour une description de ces macros de conversion de texte, consultez [Macros de Conversion de chaînes de MFC et ATL](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Exemple  
 Consultez la page [ATL et MFC Macros de Conversion de chaînes](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) pour obtenir un exemple d’utilisation de ces macros de conversion de chaînes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlconv.h  
  
##  <a name="a-nameca2caexa--ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX  
 Constructeur.  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne de texte à convertir.  
  
 `nCodePage`  
 N’est pas utilisé dans cette classe.  
  
### <a name="remarks"></a>Remarques  
 Crée la mémoire tampon requise pour la traduction.  
  
##  <a name="a-namedtora--ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX :: ~ CA2CAEX  
 Destructeur.  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère la mémoire tampon allouée.  
  
##  <a name="a-namempsza--ca2caexmpsz"></a><a name="m_psz"></a>CA2CAEX::m_psz  
 Le membre de données qui stocke la chaîne source.  
  
```
LPCSTR m_psz;
```  
  
##  <a name="a-nameoperatorlpcstra--ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX::operator LPCSTR  
 Opérateur de conversion.  
  
```  
operator LPCSTR() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la chaîne de texte en tant que type `LPCSTR`.  
  
## <a name="see-also"></a>Voir aussi  
 [CA2AEX (classe)](../../atl/reference/ca2aex-class.md)   
 [CA2WEX (classe)](../../atl/reference/ca2wex-class.md)   
 [CW2AEX (classe)](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX (classe)](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX (classe)](../../atl/reference/cw2wex-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

