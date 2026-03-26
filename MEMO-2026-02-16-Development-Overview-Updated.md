<div align="center">

# PointSav Digital Systems AG
### *Development Overview & Operational Showcase / Visión General del Desarrollo y Muestra Operativa*

</div>

**Company:** PointSav Digital Systems AG
**Contact:** IT Support (System Architecture) / Soporte TI (Arquitectura del Sistema)
**Date:** February 16, 2026 (Updated March 2026)
**Subject:** Development Overview & Operational Showcase

---

## 1. DEVELOPMENT OVERVIEW / VISIÓN GENERAL DEL DESARROLLO

### Corporate Entity Relationships / Relaciones de Entidades Corporativas
* **Vendor:** PointSav Digital Systems AG (“PointSav”).
* **Primary Customer:** Woodfine Management Corp. (“Woodfine”).
* **Parent Company:** Woodfine Capital Projects Inc. (“Parent Company”) Owns 100% of PointSav and Woodfine.
* **Ethics & Oversight:** Sovereign Data Foundation. Holds 10% equity; overseer of open-source integrity.

### Glossary / Glosario
* **Totebox Orchestration:** The complete environment for independent data storage.
* **Private Network:** The physical/virtual routing layer for scaling an orchestration.
* **Totebox Archive:** An isolated container for a specific data entity.
* **The Diode Standard:** A universal one-way command flow from startpoints to endpoints.
* **Machine-Based Authorization (MBA):** Permission granted via hardware pairing (system-security), not usernames/passwords.

### Commercial Strategy & System Matrix / Estrategia Comercial y Matriz del Sistema
| System / Sistema | License | Status | Commercial Logic |
| :--- | :--- | :--- | :--- |
| `os-totebox` | Apache 2.0 | Free | Data segregation |
| `os-console` | Apache 2.0 | Free | Graphical terminal |
| `os-workplace` | Apache 2.0 | Free | Desktop Environment |
| `os-infrastructure` | Proprietary | Paid | Infrastructure node provisioning |
| `os-interface` | Proprietary | Paid | Aggregation of Totebox Archives |
| `os-network-admin` | Proprietary | Paid | Private network routing and policy |
| `os-mediakit` | Proprietary | Paid | Compliance/Investor Relations |
| `os-privategit` | Apache 2.0 | Free | Version Control |

---

## 2. SOFTWARE ARCHITECTURE / ARQUITECTURA DE SOFTWARE

### The PointSav Monorepo — seL4 Foundation / El Monorepo PointSav
PointSav replaces generic OS layers with a custom Capability-Based Manager in `no_std` Rust to ensure full-stack control within the `pointsav-monorepo`.
* **Layer 0 (`system-substrate`):** Mathematically verified seL4/C core. Root of Trust. Expanded to include bare-metal bridges (`system-substrate-freebsd`, `system-substrate-broadcom`).
* **Layer 1 (`system-foundation` & `system-core`):** Proprietary Rust `no_std`. Manages hardware resources.
* **Layer 2 (`system-security`):** Proprietary Rust Capability Monitor. Replaces third-party frameworks.
* **Layer 3 (`os-guest`):** Isolated Protection Domains (PDs) running specialized workloads.

### Technical Doctrine / Doctrina Técnica
* **The Crate System:** The package-system is the mandatory foundation for all PointSav operating systems.
* **Capability Management:** Abstracts seL4 system calls into safe Rust via `system-security`.
* **Hardware Abstraction Layer (HAL):** Standardizes drivers via `system-substrate`.
* **User Interface:** Unified `os-console` execution utilizing Micro-Frontend UI plugins (`app-console-*`).

---

## 3. THE 3-LAYER STACK / LA PILA DE 3 NIVELES
A model that decouples the "Logic" (VMs) from the "Metal" (Infrastructure), allowing your personal digital environment to be truly cloud-agnostic and freely transferable.

### Infrastructure Layer (Private Network) / Capa de Infraestructura
* **`os-infrastructure`:** A lightweight, universal hypervisor designed to be installed on any hardware.
* **Boot & Phone Home:** Performs a cryptographic handshake to join the Private Network.
* **Stateless Node:** Holds no user data. Simply provides compute and RAM.
* **`os-network-admin`:** Orchestrates the "Map" of where VMs are running and authorizes provisioning.

### Platform Layer (Portable Unikernels) / Capa de Plataforma
These are your "Independent Micro-VMs".
* **`os-totebox`:** Core hardware-agnostic micro-kernel foundation.
* **`os-interface`:** Totebox Archive aggregation.
* **`os-mediakit`:** High-performance, "Just-Enough-OS" (JeOS) designed for corporate disclosure.
* **`os-privategit`:** The independent code repository.

### Delivery Layer (User Terminals) / Capa de Entrega
* **`os-workplace` (Type I):** A bare-metal installation on trusted hardware. Boots directly into `os-console`.
* **`os-console` (Type II):** A hosted application/window running on top of a legacy OS (The Command Ledger).

---

## 4. WOODFINE DEPLOYMENTS / DESPLIEGUES WOODFINE

### Infrastructure (Private Network) / Infraestructura
| Deployment Name | Operating System | App Variant | Role | Connection |
| :--- | :--- | :--- | :--- | :--- |
| `fleet-infrastructure-onprem` | `os-infrastructure` | `app-infrastructure-onprem` | Physical Office Server | `os-network-admin` |
| `fleet-infrastructure-leased` | `os-infrastructure` | `app-infrastructure-leased` | Dedicated Leased Server | `os-network-admin` |
| `fleet-infrastructure-cloud` | `os-infrastructure` | `app-infrastructure-cloud` | Virtualized Instance | `os-network-admin` |
| `route-network-admin` | `os-network-admin` | null | Network Administration | Fleet |

### Platform and Delivery (Totebox Orchestration) / Plataforma y Entrega
| Name | Operating System | App Variant | Role | Connection |
| :--- | :--- | :--- | :--- | :--- |
| `gateway-interface-command` | `os-interface` | `app-command-center` | Aggregation | Totebox Archives |
| `cluster-totebox-corporate` | `os-totebox` | `app-totebox-corporate` | Corporate | `os-interface` |
| `cluster-totebox-real-property` | `os-totebox` | `app-totebox-real-property` | Real Property | `os-interface` |
| `cluster-totebox-personnel` | `os-totebox` | `app-totebox-personnel` | Personnel | `os-interface` |
| `node-console-operator` | `os-console` | `app-console-*` | Unified Terminal | `os-interface` |

### Independent Systems / Sistemas Independientes
| System Target | Operating System | App Variant | Role | Production URL |
| :--- | :--- | :--- | :--- | :--- |
| `media-marketing-landing` | `os-mediakit` | `app-marketing` | Landing Page | woodfinegroup.com |
| `media-knowledge-corporate` | `os-mediakit` | `app-knowledge` | Corporate Wiki | corporate.woodfinegroup.com |
| `media-knowledge-projects` | `os-mediakit` | `app-knowledge` | Project Wiki | projects.woodfinegroup.com |
| `media-knowledge-distribution` | `os-mediakit` | `app-distribution` | Newsroom | news.woodfinegroup.com |
| `vault-privategit-source` | `os-privategit` | `app-source-control` | Source Control | Internal / On-Prem |

---

## 5. POINTSAV DEPLOYMENTS / DESPLIEGUES POINTSAV

### Independent Systems / Sistemas Independientes
| System Target | Operating System | App Variant | Role | Production URL |
| :--- | :--- | :--- | :--- | :--- |
| `media-marketing-landing` | `os-mediakit` | `app-marketing` | Landing Page | pointsav.com |
| `media-knowledge-documentation` | `os-mediakit` | `app-knowledge` | Documentation Wiki | documentation.pointsav.com |
| `media-knowledge-distribution` | `os-mediakit` | `app-distribution` | Newsroom | news.pointsav.com |
| `vault-privategit-source` | `os-privategit` | `app-source-control` | Source Control | Internal / On-Prem |
| `vault-privategit-design-system` | `os-privategit` | `app-design-system` | Design System | design.pointsav.com |

---

## 6. ENGINEERING TO DATE / INGENIERÍA HASTA LA FECHA

### 6.1 ACTIVE SUPPORT (LTS) — pointsav-monorepo
The monorepo root acts as the base, containing the third-party foreign ingredients, the proprietary build tools, and the proprietary blueprints required to forge a bootable OS image.
* **`system-substrate`**: The official C-based microkernel (Legacy seL4) and physical hardware bridges.
* **`moonshot-toolkit`**: The Rust CLI that orchestrates the build process.
* **`system-core` & `system-foundation`**: Universal structs, execution parameters, and Errors.
* **`system-security`**: Capability handshakes and cryptographic pairing.
* **`system-interface`**: Pure software math for drawing pixels (Rasterizer/Layout).

### 6.2 INDEPENDENT SYSTEMS / SISTEMAS INDEPENDIENTES
These systems are designed to run with or without a Totebox Orchestration or Private Network.
* **`os-mediakit`**: A high-performance, "Just-Enough-OS" (JeOS) designed to deliver the absolute best environment for corporate disclosure and digital marketing. Includes payload processing tools like `app-mediakit-telemetry`.
* **`os-privategit`**: The sovereign code repository and build server. Includes `app-source-control` and `app-design-system`.

### 6.3 TOTEBOX SERVICES / SERVICIOS TOTEBOX
* **`service-content`**: Specialized engine for structural synthesis of institutional knowledge. Manages governing rules, synthesizes memos, and handles cross-language parity.
* **`service-people`**: A human-centric service designed to distill raw digital signals into a deterministic, private personnel substrate.
* **`service-email`**: An independent email bridge designed to ensure 100% on-prem ownership of Microsoft 365 Exchange data using the Maildir format.
* **`service-slm`**: Sovereign AI Routing Engine. Safely processes linguistic intelligence while isolating the microkernel from external models.

---

## 7. MOONSHOTS & VENDOR QUARANTINES / PROYECTOS ESPECIALES Y CUARENTENAS

This register tracks every component where we currently rely on "Foreign" technology. Each entry represents active debt to be paid by building an independent native replacement.

### Vendor Quarantines (Legacy Dependencies)
| Quarantined Component | Functional Role | Isolation Strategy |
| :--- | :--- | :--- |
| `vendor-sel4-kernel` | Legacy Microkernel | Slated for replacement by `moonshot-kernel`. |
| `vendor-virtio` | Virtualization Bridge | Nested execution on `system-substrate-freebsd`. |
| `vendor-azure-auth` | Commercial Identity | Quarantined outside the core microkernel. |
| `vendor-microsoft-graph` | External Mail API | Used strictly by `service-email` bridge. |
| `vendor-gpu-drivers` | Legacy Video | Slated for Project X-Ray replacement. |

### Active Sovereign Replacements (Moonshots)
| Component | Current Vendor | Moonshot Project |
| :--- | :--- | :--- |
| **Kernel** | seL4 (C-Language) | `moonshot-kernel` (Project Vector: No_std Rust). |
| **Hypervisor** | seL4 VMM (C-Libs) | `moonshot-hypervisor` & `moonshot-sel4-vmm` (Rust VMM). |
| **Video Driver** | UEFI GOP (Firmware) | `moonshot-gpu` (Project X-Ray: Native Drivers). |
| **Build System** | Microkit (Python/CMake) | `moonshot-toolkit` (Rust-Only Toolchain). |
| **Database** | Sled (Embedded DB) | `moonshot-database` (PSDB: Capability-aware). |
| **Search/Index** | Tantivy / Regex | `moonshot-index` (Deterministic Indexing). |
| **Network/Protocol** | MS Exchange / IMAP | `moonshot-network` & `moonshot-protocol`. |

---
*© 2026 PointSav Digital Systems™.*
*Public Architectural Blueprint. Governed by the Sovereign Data Protocol.*
