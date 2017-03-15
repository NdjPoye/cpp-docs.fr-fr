---
title: Classe de CA2WEX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATLCONV/CA2WEX
- ATL.CA2WEX
- ATL.CA2WEX<t_nBufferLength>
- ATL::CA2WEX
- ATL::CA2WEX<t_nBufferLength>
- CA2WEX
dev_langs:
- C++
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7c1029d0d9cb1abb1980f97c9541e2c1ce40b539
ms.lasthandoff: 02/24/2017

---
# <a name="ca2wex-class"></a>CA2WEX (classe)
Cette classe est utilisée par les macros de conversion de chaînes `CA2TEX`, `CA2CTEX`, `CT2WEX`, et `CT2CWEX`et le typedef **CA2W**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction. La longueur par défaut est 128 octets.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](#ca2wex)|Constructeur.|  
|[CA2WEX :: ~ CA2WEX](#dtor)|Destructeur.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|Opérateur de conversion.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CA2WEX::m_psz](#m_psz)|Le membre de données qui stocke la chaîne source.|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|La mémoire tampon statique, utilisé pour stocker la chaîne convertie.|  
  
## <a name="remarks"></a>Remarques  
 À moins que des fonctionnalités supplémentaires sont requises, utilisez `CA2TEX`, `CA2CTEX`, `CT2WEX`, `CT2CWEX`, ou **CA2W** dans votre code.  
  
 Cette classe contient une mémoire tampon de taille fixe statique qui est utilisé pour stocker le résultat de la conversion. Si le résultat est trop grand pour tenir dans la mémoire tampon statique, la classe alloue de la mémoire avec `malloc` et libère la mémoire quand l'objet passe en dehors de l'étendue. Cela garantit que, contrairement au texte de macros de conversion disponibles dans les versions précédentes d’ATL, cette classe est sûr à utiliser dans des boucles et qu’il ne dépassement de la pile.  
  
 Si la classe tente d’allouer de la mémoire sur le tas et échoue, il appellera `AtlThrow` avec un argument de **E_OUTOFMEMORY**.  
  
 Par défaut, les classes de conversion ATL et les macros utilisent la page de codes ANSI du thread actuel pour la conversion. Si vous souhaitez substituer ce comportement pour une conversion spécifique, spécifiez la page de codes comme second paramètre au constructeur de la classe.  
  
 Les macros suivantes sont basées sur cette classe :  
  
- `CA2TEX`  
  
- `CA2CTEX`  
  
- `CT2WEX`  
  
- `CT2CWEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
- **CA2W**  
  
 Pour une description de ces macros de conversion de texte, consultez [Macros de Conversion de chaînes de MFC et ATL](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Exemple  
 Consultez la page [ATL et MFC Macros de Conversion de chaînes](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) pour obtenir un exemple d’utilisation de ces macros de conversion de chaînes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlconv.h  
  
##  <a name="a-nameca2wexa--ca2wexca2wex"></a><a name="ca2wex"></a>CA2WEX::CA2WEX  
 Constructeur.  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne de texte à convertir.  
  
 `nCodePage`  
 La page de codes utilisée pour effectuer la conversion. Consultez la discussion de paramètre de page de code pour le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] fonction [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) pour plus de détails.  
  
### <a name="remarks"></a>Remarques  
 Alloue de la mémoire tampon utilisée dans le processus de traduction.  
  
##  <a name="a-namedtora--ca2wexca2wex"></a><a name="dtor"></a>CA2WEX :: ~ CA2WEX  
 Destructeur.  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère la mémoire tampon allouée.  
  
##  <a name="a-namempsza--ca2wexmpsz"></a><a name="m_psz"></a>CA2WEX::m_psz  
 Le membre de données qui stocke la chaîne source.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="a-namemszbuffera--ca2wexmszbuffer"></a><a name="m_szbuffer"></a>CA2WEX::m_szBuffer  
 La mémoire tampon statique, utilisé pour stocker la chaîne convertie.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="a-nameoperatorlpwstra--ca2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CA2WEX::operator LPWSTR  
 Opérateur de conversion.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la chaîne de texte en tant que type **LPWSTR.**  
  
## <a name="see-also"></a>Voir aussi  
 [CA2AEX (classe)](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX (classe)](../../atl/reference/ca2caex-class.md)   
 [CW2AEX (classe)](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX (classe)](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX (classe)](../../atl/reference/cw2wex-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

