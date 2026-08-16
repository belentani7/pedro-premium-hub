# EXTRACCION COMPLETA: git.txt
> Extraído el 2026-07-25. Fuente: C:\Users\USER\Desktop\git.txt

---

## 1. PROYECTOS DE SOFTWARE (Ideas Principales)

### 1.1 Nexus Workforce Enterprise (SaaS RRHH)
- Dashboard operacional con KPIs (plantilla activa, gasto horas extra, cumplimiento legal, coste laboral)
- Planificación de turnos automáticos (rotativos: mañana/tarde/noche)
- Gestión de incidencias masivas (mantenimiento, auditorías, crisis)
- Simulador de nómina y costes laborales
- **Stack**: Python + pywebview → ejecutable .exe independiente
- **Archivos clave**: `app.html`, `main.py`, `nexus_enterprise.py`

### 1.2 Claude Code Sentinel (Plugin de Seguridad)
- Sistema inmune contra recursión infinita de subagentes
- Detección de quema de tokens (4M tokens en 5 min)
- Checkpoints automáticos al interrumpir
- Comando `/sentinel:brake` para freno de emergencia
- **Stack**: Plugin Claude Code (skills + hooks + subagentes + scripts bash)

### 1.3 Motor Legal Laboral Español
- Implementación del Estatuto de los Trabajadores en código
- Convenios colectivos (Call Center BCN, Comercio, Oficinas, Hostelería, Contact Center)
- Permisos retribuidos (Art. 37 ET)
- Validación automática de turnos y descansos
- **Stack**: Python con dataclasses, tipado estricto

### 1.4 Motor de Reservas de Viaje con IA
- Bypass de comisiones Expedia/Airbnb (15-20% ahorro)
- Scraping de precios con Playwright/Selenium
- Reserva directa en sitios de propietarios
- Negociación por voz AI (Vapi/Retell/Bland)
- **Stack**: AI agents + browser automation + voice AI

---

## 2. REPOSITORIOS GIT (100+ listados)

### Marketplaces y Colecciones Curadas
| # | Repo | Descripción |
|---|------|-------------|
| 1 | anthropics/claude-code | CLI oficial de Anthropic |
| 3 | barnburner121/claude-plugin-marketplace | 500+ plugins, 600+ herramientas MCP |
| 4 | danielrosehill/Claude-Code-Plugins | Marketplace completo |
| 5 | rdmgator12/awesome-claude-plugins | 132 bundles (skills, MCP, hooks) |
| 6 | subinium/awesome-claude-code | 1000+ estrellas, herramientas curadas |
| 10 | claude-plugins-official | Directorio oficial (30.1k ⭐) |
| 16 | Mizoreww/awesome-claude-code-config | 25 plugins curados, config lista |
| 17 | ithiria894/awesome-claude-code-workflows | Recetas de workflows |

### Skills (Colecciones Masivas)
| # | Repo | Descripción |
|---|------|-------------|
| 23 | artubss/SKILLS-CLAUDE-CODE | 1,044+ skills, 400+ subagentes, 341 slash-commands |
| 24 | rohitg00/awesome-claude-code-toolkit | 135 agentes, 35 skills, 176+ plugins |
| 25 | Kevinchamplin/claude-skills | Skills listas para copiar |
| 26 | secondsky/claude-skills | 170 skills probadas en producción |
| 27 | laolaoshiren/claude-code-skills-zh | 100+ skills en chino |
| 35 | ariadoss/superskills | TDD, debugging, seguridad |

### Subagentes
| # | Repo | Descripción |
|---|------|-------------|
| 42 | 0xfurai/claude-code-subagents | 100+ subagentes producción |
| 43 | elazzi/awesome-claude-code-subagents | 100+ por caso de uso |
| 47 | gruckion/nested-subagent | Subagentes anidados |
| 49 | zircote/.claude | 100+ agentes por dominio |

### Hooks
| # | Repo | Descripción |
|---|------|-------------|
| 50 | karanb192/claude-code-hooks | Seguridad, costos, observabilidad |
| 51 | Payshak/claude-hook-kit | SDK TypeScript tipado |
| 54 | miyaoka/claude-hooks | Control de ejecución de herramientas |

### MCP Servers
| # | Repo | Descripción |
|---|------|-------------|
| 67 | KunihiroS/claude-code-mcp | explain_code, review_code, fix_code |
| 68 | jaenster/puppeteer-mcp-claude | Automatización navegador |
| 70 | eliasonAdvising/claude-memory-mcp | Memoria persistente con grafos |
| 71 | JONGSEO-YOON/multi-llm-mcp | GPT y Gemini dentro de Claude |

### Plugins Destacados
| # | Repo | Descripción |
|---|------|-------------|
| 56 | 2389-research/claude-plugins | 28 plugins, TDD, multi-agente |
| 57 | FlorianBruniaux/claude-code-plugins | 212 templates en 8 plugins |
| 62 | tmdgusya/claude-hammer | worker-validator-critic + gates |
| 96 | claude-code-mcp (KunihiroS) | MCP server con 7 herramientas |

### Issues Críticos
| # | Issue | Descripción |
|---|-------|-------------|
| 90 | anthropics/claude-code#68430 | Bug spawn recursivo subagentes |
| 91 | anthropics/claude-code#29455 | Guía .claudeignore |

---

## 3. SKILLS DE CLAUDE CODE (Identificadas)

### Skills del Plugin Sentinel
| Skill | Comando | Propósito |
|-------|---------|-----------|
| sentinel-brake | `/sentinel:brake` | Freno de emergencia, detiene todo |
| sentinel-audit | `/sentinel:audit` | Auditoría de salud del sistema |
| sentinel-recover | `/sentinel:recover` | Recuperación desde checkpoints |

### Skills de MiMoCode (Disponibles en este sistema)
| Categoría | Skills |
|-----------|--------|
| **Frontend** | react-expert, vue-expert, angular-architect, nextjs-developer, senior-frontend |
| **Backend** | backend-expert, senior-backend, senior-fullstack |
| **Design** | ui-ux-pro-max, frontend-design, design-system, interface-design, design-intelligence |
| **Testing** | test-master, test-driven-development, playwright-expert |
| **Security** | secure-code-guardian, security-scanner, skill-security-auditor |
| **Research** | deep-research, super-research, arxiv |
| **DevOps** | mcp-server-builder, loop, workflow-orchestrator |
| **Code Quality** | code-reviewer, karpathy-coder, zero-hallucination-coder, anti-overengineering |
| **PDF/Docs** | pdf-generator, pdf-official, docx-official, pptx-official, xlsx-official |
| **Skills System** | skill-creator, writing-skills, skill-installer, mimocode |

---

## 4. CODIGO PYTHON UTIL (Del archivo)

### 4.1 Nexus Enterprise (GUI Desktop)
```python
# Estructura: nexus_enterprise.py
# - NexusDatabase: SQLite local con persistencia
# - PayrollEngine: Motor de cálculo de nóminas
# - HRController: Lógica de ausencias (Art. 37 ET)
# - NexusEnterpriseGUI: Interfaz tkinter con tabs
# Compilar: pyinstaller --noconsole --onefile --windowed Nexus_Enterprise.exe
```

### 4.2 Motor Legal Laboral
```python
# Estructura: motor_legal.py
# - EstatutoTrabajadores: Leyes marco (frozen dataclass)
# - LegisAutonomica: Variables por CCAA
# - ConvenioColectivo: Sectoriales/Provinciales
# - Empleado: Entidad con datos del trabajador
# - MotorValidacionLegal: Cálculo automático
```

### 4.3 Motor de Nómina con Convenios
```python
# Convenios implementados:
# - cc_bcn: Call Center BCN (22d vac, 15.50€ plus noct, 14% IRPF)
# - comercio: Comercio BCN (30d vac, 15% IRPF)
# - oficinas: Oficinas y Despachos (23d vac, 18% IRPF)
# - HOSTELERIA_CAT: Hostelería Catalunya (30d vac, 25% plus noct)
# - CONTACT_CENTER_ES: Contact Center Estatal (32d vac, pausa PVD 5min)
```

---

## 5. PROBLEMAS DOCUMENTADOS DE CLAUDE CODE

### Críticos
1. Recursión infinita de subagentes (50+ niveles)
2. Consumo masivo de tokens (4M en 5 min)
3. Pérdida de trabajo en interrupciones
4. Ignora `CLAUDE_CODE_FORK_SUBAGENT=0`
5. Fetch ineficiente (archivos uno por uno vía HTTP)

### Estabilidad
6. Caídas del servidor (500, 529)
7. Corrupción de `.claude.json` (múltiples instancias)
8. Problemas de permisos en bucles infinitos
9. Autocompact prematuro (~195K tokens)

### Seguridad
10. Vulnerabilidad de "puerta trasera" (alerta China)
11. Filtración de datos sin consentimiento
12. Prohibiciones empresariales (Alibaba)

---

## 6. SOLUCIONES Y MEJORES PRÁCTICAS

### Gestión de Contexto
- Usar `/clear` para empezar de cero
- Usar `/compact` para resumir
- Crear `.claudeignore` para excluir directorios
- Minimizar uso de MCPs innecesarios

### Optimización de Tokens
- Filtrar lo que Claude ve (`.claudeignore`)
- Limitar búsquedas grep
- Actualizar a última versión (bugs de caché parcheados)
- Usar subagentes para tareas aisladas

### Configuración Recomendada
```json
{
  "env": {
    "CLAUDE_CODE_FORK_SUBAGENT": "0",
    "SENTINEL_MAX_DEPTH": "3",
    "SENTINEL_TOKEN_LIMIT": "100000"
  }
}
```

---

## 7. TAREAS UTILES EXTRAIDAS (Máximo esfuerzo)

### Inmediatas (Hoy)
1. [ ] Crear estructura del plugin `claude-code-sentinel`
2. [ ] Implementar skill `/sentinel:brake`
3. [ ] Implementar skill `/sentinel:audit`
4. [ ] Implementar skill `/sentinel:recover`
5. [ ] Crear scripts bash de soporte (check-recursion, token-monitor, checkpoint-save)
6. [ ] Configurar hooks en `hooks.json`
7. [ ] Crear subagente `sentinel-guard`

### Corto Plazo (Esta semana)
8. [ ] Crear `.claudeignore` para optimizar contexto
9. [ ] Configurar permisos en `settings.json`
10. [ ] Implementar Nexus Enterprise como ejecutable .exe
11. [ ] Crear motor legal laboral con todos los convenios
12. [ ] Documentar los 100 repositorios en un README organizado

### Mediano Plazo (Este mes)
13. [ ] Publicar plugin en marketplace
14. [ ] Crear tests para el plugin
15. [ ] Implementar motor de reservas de viaje con IA
16. [ ] Crear skills personalizadas para flujos repetitivos
17. [ ] Configurar subagentes especializados por tarea

---

## 8. COMANDOS CLAUDE CODE ESENCIALES

| Comando | Uso |
|---------|-----|
| `/init` | Genera CLAUDE.md inicial |
| `/memory` | Refina memoria del proyecto |
| `/mcp` | Configura servidores MCP |
| `/plan` | Modo planificación |
| `/model` | Cambia el modelo |
| `/effort` | Ajusta nivel de razonamiento |
| `/compact` | Resume para liberar espacio |
| `/diff` | Muestra lo que cambió |
| `/code-review` | Revisa el diff |
| `/security-review` | Revisa vulnerabilidades |
| `/rewind` | Deshace hasta checkpoint |
| `/doctor` | Diagnostica problemas |
| `/usage` | Estadísticas de tokens |
| `/clear` | Nueva tarea limpia |
| `/resume` | Vuelve a conversación anterior |

---

## 9. PRECIOS Y PLANES

| Plan | Precio | Uso |
|------|--------|-----|
| Pro | $20/mes | Incluye Claude Code |
| Max 5x | $100/mes | 5x uso de Pro |
| Max 20x | $200/mes | 20x uso de Pro |
| Team | $20-25/seat | Para equipos |
| Team Premium | $100-125/seat | 5x uso Team |

---

## 10. REFERENCIAS Y FUENTES

- Documentación oficial: code.claude.com/docs
- Plugins: code.claude.com/docs/en/plugins
- Skills: code.claude.com/docs/en/skills
- Hooks: code.claude.com/docs/en/hooks
- Issue #68430: github.com/anthropics/claude-code/issues/68430
- superpowers: github.com/dorucioclea/superpowers
