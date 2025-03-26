# EthEcuador DAO: Yellow Paper

## Resumen

Este documento detalla la arquitectura técnica, económica y de gobernanza de EthEcuador DAO, una organización autónoma descentralizada diseñada para fomentar el crecimiento del ecosistema web3 en Ecuador. A través de mecanismos de incentivos tokenizados, sistemas de votación descentralizados y gestión transparente del tesoro, EthEcuador DAO establece un marco para la participación comunitaria, la toma de decisiones colectivas y el desarrollo de proyectos con impacto local.

## 1. Introducción

EthEcuador DAO es una organización representada por reglas codificadas en contratos inteligentes, caracterizada por su transparencia, resistencia a la censura y gobernanza descentralizada. La DAO busca aumentar el compromiso y sentido de pertenencia de los miembros de la comunidad mediante el uso de plataformas web3, promoviendo la transparencia, descentralización e inclusión en todos sus procesos.

## 2. Principios Fundamentales

La arquitectura de EthEcuador DAO se basa en los siguientes principios:

1. **Descentralización**: La toma de decisiones debe distribuirse entre los miembros de la comunidad.
2. **Transparencia**: Todas las operaciones, transacciones y decisiones deben ser verificables en la blockchain.
3. **Meritocracia**: Las contribuciones a la comunidad son reconocidas y recompensadas proporcionalmente.
4. **Sostenibilidad**: La estructura económica debe garantizar la viabilidad a largo plazo de la organización.
5. **Inclusividad**: Barreras mínimas de entrada para nuevos miembros de la comunidad.

## 3. Arquitectura Técnica

### 3.1 Red de Despliegue

La infraestructura de la DAO se ha implementado en **Arbitrum**, una solución Layer 2 para Ethereum, seleccionada por sus ventajas:

- Bajos costos de transacción en comparación con Ethereum mainnet
- Alta seguridad heredada de Ethereum
- Ecosistema establecido de herramientas para DAOs
- Compatibilidad completa con estándares ERC-20 y ERC-721
- Tiempos de confirmación rápidos

### 3.2 Plataforma de Gestión

La DAO utiliza **Aragon** como plataforma principal para su creación y administración, aprovechando sus características:

- Interfaz intuitiva para creación y gestión de DAOs
- Módulos preconfigurados para votación, finanzas y membresías
- Amplia compatibilidad con Arbitrum
- Herramientas de gestión de tesoro integradas
- Capacidad de extensión mediante plugins personalizados

### 3.3 Componentes del Sistema

#### 3.3.1 Contratos Inteligentes

El sistema consta de los siguientes contratos inteligentes interconectados:

```mermaid
flowchart TB
    A[TokenContract] -->|Gestiona| B[Tokens LATA]
    C[GovernanceContract] -->|Utiliza| A
    D[TreasuryContract] -->|Administra| E[Tesoro de la DAO]
    F[ProjectFundingContract] -->|Financia| G[Proyectos]
    F -->|Contribuye 10%| D
    C -->|Propuestas aprobadas| D
    D -->|Ejecuta| F
```

1. **TokenContract**: Implementación ERC-20 del token de gobernanza LATA.
   - Funciones de emisión controlada
   - Mecanismos de distribución automatizada
   - Interfaz para consulta de balances y derechos de voto

2. **GovernanceContract**: Sistema de propuestas y votación.
   - Presentación y gestión de propuestas
   - Votación ponderada por tokens
   - Ejecución automática de propuestas aprobadas

3. **TreasuryContract**: Gestión de fondos comunitarios.
   - Interfaz para multisig de firmantes autorizados
   - Registro transparente de ingresos y gastos
   - Automatización de distribuciones y contribuciones

4. **ProjectFundingContract**: Financiamiento y gestión de proyectos.
   - Solicitud de fondos para proyectos
   - Distribución de pagos a ejecutores
   - Contribución automática del 10% al tesoro

### 3.4 Consejo de Gobernanza y Billetera Multi-firma

La gestión del tesoro y la administración de la DAO se realiza mediante un Consejo de Gobernanza que utiliza una billetera multi-firma en Arbitrum para ejecutar las decisiones aprobadas. El Consejo de Gobernanza fue formado a través de una convocatoria abierta realizada en el canal de Telegram del equipo núcleo, y está compuesto por siete miembros: Alex, Nico, Chris, Marcos, Nathalia, Paul y David. Este consejo y su billetera asociada tienen la capacidad de:

- Ejecutar decisiones aprobadas mediante votación
- Gestionar los fondos del tesoro
- Realizar actualizaciones técnicas cuando sea necesario
- Responder a situaciones de emergencia

## 4. Modelo Económico

### 4.1 Tokenomics

#### 4.1.1 Token de Gobernanza

- **Nombre y Símbolo**: LATA
- **Descripción**: Inspirado en la expresión coloquial ecuatoriana para referirse a la moneda "Sucre"
- **Estándar**: ERC-20 con extensión ERC-20Votes en Arbitrum
- **Divisibilidad**: 18 decimales
- **Suministro Total Inicial**: 10,000 LATA
- **Características Especiales**: Sistema de delegación de votos integrado

#### 4.1.2 Distribución Inicial

El suministro inicial de 10,000 LATA se distribuye de la siguiente manera:

```mermaid
pie
    title "Distribución Inicial de Tokens LATA"
    "Tesoro de la DAO" : 5000
    "Equipo Núcleo" : 1000
    "Comunidad Telegram" : 1000
    "Donadores" : 1000
    "Bóveda de Meritocracia" : 2000
```

1. **Tesoro de la DAO**: 5,000 LATA (50%)
   - Gestionado mediante la billetera multi-firma
   - Destinado a financiar proyectos comunitarios y operaciones

2. **Equipo Núcleo**: 1,000 LATA (10%)
   - 17 miembros activos × 58.82 LATAs cada uno (redondeado)
   - Incluye fundadores y contribuyentes principales

3. **Comunidad Telegram**: 1,000 LATA (10%)
   - 128 miembros × 1 LATA cada uno 
   - Distribución por miembro activo mediante proceso de verificación
   - El resto de tokens quedan para posibles futuros miembros de la comunidad telegram

4. **Donadores**: 1,000 LATA (10%)
   - Reservado para recompensar donaciones económicas iniciales
   - Tasa de distribución: 1 LATA por 100 USD donado
   - La distribución de los tokens de governanza es simbólica para los donadores, ya que se incentiva meritocracia por sobre lo económico

5. **Bóveda de Meritocracia**: 2,000 LATA (20%)
   - Reservado para recompensar contribuciones meritorias
   - Mayor tasa de recompensa que las donaciones económicas

#### 4.1.3 Distribución expandida (post-lanzamiento)

Para acomodar la distribución a la comunidad de X (756 seguidores), se contempla una emisión adicional controlada:

- Programa de airdrop verificado
- Requisito de interacción con la DAO para reclamar tokens
- Límite de 1 LATA por seguidor verificado

#### 4.1.4 Generación Continua

```mermaid
graph LR
    A[Contribuciones Meritocráticas] -->|Alta recompensa| D[Emisión de LATA]
    B[Donaciones al Tesoro] -->|10 LATA por USD| D
    C[Proyectos Comunitarios] -->|20 LATA por USD generado| D
    C -->|10% de ingresos| E[Tesoro DAO]
```

La emisión de tokens post-lanzamiento se produce mediante:

1. **Recompensas por Contribuciones Meritocráticas**:
   - Organización de eventos: 100 LATA por evento pequeño (escalable según impacto)
   - Desarrollo técnico: LATA proporcionales al esfuerzo y valor generado
   - Gestión comunitaria: LATA por tareas administrativas y de coordinación
   - *Valoración superior a las recompensas por donaciones económicas*

2. **Donaciones al Tesoro**:
   - Tasa de conversión base: 10 LATA por cada 1 USD donado
   - Mecanismo implementado mediante contrato inteligente

3. **Contribuciones de Proyectos**:
   - 20 LATA por cada 1 USD generado por proyectos comunitarios
   - 10% de ingresos de proyectos destinado automáticamente al tesoro

### 4.2 Modelo de Sostenibilidad

La sostenibilidad financiera de la DAO se basa en:

1. **Donaciones Directas**: Contribuciones voluntarias al tesoro
2. **Porcentaje de Proyectos**: 10% de los ingresos de proyectos comunitarios
3. **Grants y Financiamiento Externo**: Subvenciones de fundaciones y ecosistemas blockchain

## 5. Sistema de Gobernanza

### 5.1 Estructura de Decisiones

```mermaid
stateDiagram-v2
    [*] --> Creación: Propuesta creada
    Creación --> Discusión: Período de debate
    Discusión --> Votación: Inicio de votación
    Votación --> Rechazada: No alcanza quórum/umbral
    Votación --> Aprobada: Supera quórum/umbral
    Aprobada --> Consejo: Evaluación por Consejo
    Consejo --> Automatizada: Proceso automático
    Consejo --> Manual: Acción no automatizada
    Automatizada --> Ejecución: Smart contracts
    Manual --> Ejecución: Multisig ejecuta
    Ejecución --> [*]
    Rechazada --> [*]
```

#### 5.1.1 Tipos de Propuestas

1. **Propuestas de Financiamiento**: Solicitud de fondos para proyectos o iniciativas
2. **Propuestas de Cambio de Parámetros**: Modificaciones a la configuración de la DAO
3. **Propuestas de Integración**: Incorporación de nuevas herramientas o protocolos
4. **Propuestas de Mejora**: Cambios en los procesos o contratos inteligentes

#### 5.1.2 Proceso de Votación

1. **Creación de Propuesta**: Cualquier miembro con el mínimo requerido de tokens puede crear propuestas
2. **Período de Discusión**: Tiempo asignado para debate comunitario
3. **Votación Activa**: Los titulares de tokens emiten votos ponderados (1 token = 1 voto)
4. **Ejecución**: Implementación por la multisig de propuestas aprobadas que superen el umbral de quórum

#### 5.1.3 Parámetros de Gobernanza

- **Umbral de Propuesta**: 10 LATA mínimos para presentar propuestas
- **Duración de Votación**: 5 días para período de votación
- **Quórum**: 10% de tokens participantes requeridos
- **Umbral de Aprobación**: 51% de votos afirmativos necesarios

#### 5.1.4 Delegación de Votos

```mermaid
graph LR
    A[Titular de LATA] -->|Delega poder de voto| B[Delegado]
    B -->|Vota en nombre de| A
    B -->|Mantiene sus propios votos| C[Votación]
    A -->|Mantiene propiedad de tokens| D[Tokens LATA]
```

EthEcuador DAO implementa un sistema de delegación de votos que permite a los miembros transferir su poder de voto a otros participantes sin ceder la propiedad de sus tokens. Características principales:

- **Delegación Flexible**: Cualquier titular de LATA puede delegar su poder de voto a otro miembro
- **Revocación en Cualquier Momento**: La delegación puede ser revocada por el titular original cuando lo desee
- **Delegación Parcial o Total**: Posibilidad de delegar solo una parte de los tokens
- **Transparencia**: Todas las delegaciones quedan registradas en la blockchain y son públicamente verificables
- **Sin Transferencia de Propiedad**: El delegante mantiene la propiedad completa de sus tokens
- **Delegación Transitiva**: Un delegado puede a su vez delegar los votos recibidos (configurable según preferencia comunitaria)

### 5.2 Gestión del Tesoro

#### 5.2.1 Consejo de Gobernanza

EthEcuador DAO cuenta con un Consejo de Gobernanza formado por miembros activos de la comunidad, responsables de ejecutar cualquier acción que no esté automatizada y que haya sido aprobada mediante el proceso formal de propuestas y votaciones. 

```mermaid
flowchart TD
    A[Propuesta Aprobada] --> B[Consejo de Gobernanza]
    B --> C{¿Acción Automatizada?}
    C -->|Sí| D[Ejecución por Smart Contract]
    C -->|No| E[Ejecución por Consejo]
    E --> F[Billetera Multi-firma]
    F --> G[Implementación]
```

Este consejo es responsable de:
- Interpretar y ejecutar fielmente las decisiones comunitarias
- Coordinar acciones técnicas y administrativas
- Supervisar la implementación de proyectos
- Mantener la comunicación transparente sobre las acciones ejecutadas
- Representar a la DAO en relaciones externas

Los miembros del consejo fueron elegidos tras una convocatoria abierta en el canal de Telegram del equipo núcleo, donde se evaluó su participación consistente y aportaciones significativas al proyecto.

#### 5.2.2 Billetera Multi-firma

La gestión del tesoro se realiza mediante la billetera multi-firma controlada por los siete miembros del Consejo de Gobernanza (Alex, Nico, Chris, Marcos, Nathalia, Paul y David). La configuración requiere la aprobación de un subconjunto de firmantes para ejecutar transacciones.

#### 5.2.3 Flujo de Financiamiento

1. **Recepción de Fondos**:
   - Donaciones directas
   - Contribuciones de proyectos (10% automático)
   - Subvenciones externas

2. **Desembolso de Fondos**:
   - Aprobación mediante votación
   - Ejecución por firmantes de la multisig
   - Registro transparente en la blockchain

### 5.3 Ejecución de Proyectos

#### 5.3.1 Ciclo de Vida del Proyecto

```mermaid
graph TB
    A[Propuesta] -->|Votación| B[Aprobación]
    B -->|Desembolso| C[Financiamiento]
    C -->|Desarrollo| D[Ejecución]
    D -->|10% de ingresos| E[Contribución al Tesoro]
    D -->|Por valor generado| F[Recompensa en LATA]
```

1. **Propuesta**: Presentación detallada con objetivos, presupuesto y entregables
2. **Votación**: Aprobación por la comunidad mediante votación ponderada
3. **Financiamiento**: Desembolso de fondos según hitos predefinidos
4. **Ejecución**: Desarrollo del proyecto con actualizaciones periódicas
5. **Contribución**: Devolución automática del 10% al tesoro
6. **Recompensa**: Emisión de tokens proporcionales a la contribución

#### 5.3.2 Meritocracia

La asignación de proyectos prioriza a miembros con historial comprobado de:

- Participación activa en la comunidad
- Ejecución exitosa de proyectos anteriores
- Contribuciones significativas al ecosistema

Las recompensas por contribuciones meritocráticas son significativamente mayores que las otorgadas por donaciones económicas, incentivando la participación activa sobre las contribuciones pasivas.

## 6. Implementación Técnica

### 6.1 Contratos Inteligentes

#### 6.1.1 TokenContract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Votes.sol";
import "@openzeppelin/contracts/access/AccessControl.sol";

contract LataToken is ERC20Votes, AccessControl {
    bytes32 public constant MINTER_ROLE = keccak256("MINTER_ROLE");
    
    constructor() ERC20("Lata", "LATA") ERC20Permit("Lata") {
        _grantRole(DEFAULT_ADMIN_ROLE, msg.sender);
        _grantRole(MINTER_ROLE, msg.sender);
        
        // Initial supply of 10,000 LATA
        uint256 initialSupply = 10000 * 10**decimals();
        _mint(msg.sender, initialSupply);
    }
    
    function mint(address to, uint256 amount) public onlyRole(MINTER_ROLE) {
        _mint(to, amount);
    }
    
    // The following functions are overrides required by Solidity
    function _afterTokenTransfer(address from, address to, uint256 amount) internal override(ERC20Votes) {
        super._afterTokenTransfer(from, to, amount);
    }

    function _mint(address to, uint256 amount) internal override(ERC20Votes) {
        super._mint(to, amount);
    }

    function _burn(address account, uint256 amount) internal override(ERC20Votes) {
        super._burn(account, amount);
    }
}
```

#### 6.1.2 ProjectFundingContract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/access/Ownable.sol";
import "./LataToken.sol";

contract ProjectFunding is Ownable {
    LataToken public token;
    address public treasury;
    uint256 public treasuryFeePercentage = 10;
    
    // Reward rates
    uint256 public donationRewardRate = 10; // 10 LATA per 1 USD donated
    uint256 public projectContributionRate = 20; // 20 LATA per 1 USD from projects
    
    constructor(address _token, address _treasury) {
        token = LataToken(_token);
        treasury = _treasury;
    }
    
    function executePayment(address recipient, uint256 amount) public onlyOwner {
        uint256 treasuryAmount = (amount * treasuryFeePercentage) / 100;
        uint256 recipientAmount = amount - treasuryAmount;
        
        // Transfer funds to recipient
        (bool success1, ) = recipient.call{value: recipientAmount}("");
        require(success1, "Transfer to recipient failed");
        
        // Transfer fee to treasury
        (bool success2, ) = treasury.call{value: treasuryAmount}("");
        require(success2, "Transfer to treasury failed");
        
        // Mint tokens for the recipient based on contribution rate
        uint256 tokensToMint = amount * projectContributionRate; // 20 tokens per $1
        token.mint(recipient, tokensToMint);
    }
    
    function processDonation(address donor) public payable {
        require(msg.value > 0, "Donation amount must be greater than 0");
        
        // Transfer donation to treasury
        (bool success, ) = treasury.call{value: msg.value}("");
        require(success, "Transfer to treasury failed");
        
        // Calculate tokens to mint based on USD value
        // This assumes 1 ETH = X USD, would need oracle in production
        uint256 usdValue = calculateUsdValue(msg.value);
        uint256 tokensToMint = usdValue * donationRewardRate; // 10 tokens per $1
        
        // Mint tokens for donor
        token.mint(donor, tokensToMint);
    }
    
    function calculateUsdValue(uint256 ethAmount) internal pure returns (uint256) {
        // This is a placeholder - production would use Chainlink or similar oracle
        uint256 ethUsdPrice = 3000; // Example: 1 ETH = $3000 USD
        return (ethAmount * ethUsdPrice) / 1 ether;
    }
    
    receive() external payable {
        processDonation(msg.sender);
    }
}
```

### 6.2 Estado Actual de Implementación

La DAO ha sido creada y está activa en Arbitrum utilizando la plataforma Aragon. El token LATA ha sido desplegado y la billetera multi-firma del Consejo de Gobernanza está operativa. Las etapas de implementación incluyen:

1. **Creación de la DAO**: Completada con éxito por el Consejo de Gobernanza.

2. **Configuración del Token**: El token LATA ha sido desplegado con un suministro inicial de 10,000 tokens.

3. **Distribución Inicial**: En proceso, siguiendo el modelo establecido:
   - 5,000 LATA (50%) asignados al tesoro de la DAO
   - 1,000 LATA (10%) para el equipo núcleo
   - 1,000 LATA (10%) para la comunidad de Telegram
   - 1,000 LATA (10%) para donadores
   - 2,000 LATA (20%) en la bóveda de meritocracia

4. **Próximos pasos**:
   - Activación completa de los mecanismos de gobernanza
   - Procesamiento de las primeras propuestas formales
   - Habilitación de los sistemas de recompensas por donaciones y meritocracia
   - Implementación del sistema para integrar a la comunidad de X

## 7. Conclusión

EthEcuador DAO representa un modelo innovador de organización comunitaria basada en tecnología blockchain, diseñada para fomentar la participación, reconocer contribuciones y gestionar recursos de manera transparente y descentralizada. A través de su sistema de gobernanza tokenizado y mecanismos de financiamiento automatizados, la DAO establece las bases para el crecimiento sostenible del ecosistema web3 en Ecuador.

La implementación en Arbitrum utilizando Aragon, con el token LATA como mecanismo de gobernanza, proporciona una base técnica sólida con costos operativos minimizados. El modelo de distribución equilibrado entre el tesoro, el equipo núcleo, la comunidad existente y los mecanismos de recompensa establece incentivos alineados para el crecimiento sostenible.

Este Yellow Paper establece los parámetros técnicos, económicos y de gobernanza que guían el desarrollo e implementación de EthEcuador DAO, sujetos a refinamiento mediante los propios mecanismos de gobernanza comunitaria aquí descritos.

---

*Este documento representa la especificación técnica de EthEcuador DAO y está sujeto a modificaciones a través de los procesos de gobernanza comunitaria.*