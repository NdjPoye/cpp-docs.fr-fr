---
title: Classe de CW2CWEX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATL::CW2CWEX
- ATL.CW2CWEX
- ATL.CW2CWEX<t_nBufferLength>
- ATL::CW2CWEX<t_nBufferLength>
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a85b67a58553dada36f4472ea0683e18bc775493
ms.lasthandoff: 02/24/2017

---
# <a name="cw2cwex-class"></a>CW2CWEX (classe)
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
  
## <a name="remarks"></a>Notes  
 À moins que des fonctionnalités supplémentaires sont requises, utilisez `CW2CTEX`, `CT2CWEX`, ou `CW2W` dans votre code.  
  
 Cette classe est sûr à utiliser dans des boucles et ne sont pas un dépassement de la pile. Par défaut, les classes de conversion ATL et les macros utilisent la page de codes ANSI du thread actuel pour la conversion.  
  
 Les macros suivantes sont basées sur cette classe :  
  
- `CW2CTEX`  
  
- `CT2CWEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
- `CW2W`  
  
 Pour une description de ces macros de conversion de texte, consultez [Macros de Conversion de chaînes de MFC et ATL](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Exemple  
 Consultez la page [ATL et MFC Macros de Conversion de chaînes](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) pour obtenir un exemple d’utilisation de ces macros de conversion de chaînes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlconv.h  
  
##  <a name="a-namecw2cwexa--cw2cwexcw2cwex"></a><a name="cw2cwex"></a>CW2CWEX::CW2CWEX  
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
  
##  <a name="a-namedtora--cw2cwexcw2cwex"></a><a name="dtor"></a>CW2CWEX :: ~ CW2CWEX  
 Destructeur.  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère la mémoire tampon allouée.  
  
##  <a name="a-namempsza--cw2cwexmpsz"></a><a name="m_psz"></a>CW2CWEX::m_psz  
 Le membre de données qui stocke la chaîne source.  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="a-nameoperatorlpcwstra--cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a>CW2CWEX::operator LPCWSTR  
 Opérateur de conversion.  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la chaîne de texte en tant que type **LPCWSTR.**  
  
## <a name="see-also"></a>Voir aussi  
 [CA2AEX (classe)](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX (classe)](../../atl/reference/ca2caex-class.md)   
 [CA2WEX (classe)](../../atl/reference/ca2wex-class.md)   
 [CW2AEX (classe)](../../atl/reference/cw2aex-class.md)   
 [CW2WEX (classe)](../../atl/reference/cw2wex-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

