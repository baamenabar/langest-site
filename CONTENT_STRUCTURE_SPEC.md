# Langest Site Content Structure Specification

## Overview

This document defines the content structure and organization for the Langest Hugo website. The site serves as a comprehensive resource for a fantasy RPG campaign setting, including worldbuilding materials, adventure modules, campaign management, and game mechanics.

## Core Content Philosophy

The site organizes content around three interconnected pillars:

- **World**: Foundational lore and reference material that provides the setting
- **Adventures**: Reusable story modules tied to specific locations and events
- **Campaigns**: Character-driven journeys through time, connecting multiple adventures

All three content types feed into and enrich each other, creating a living ecosystem of RPG content.

## Content Architecture

### Primary Content Types

#### 1. **World Content** (`/content/world/`)
**Purpose**: Static reference material about the fantasy world of Langest
**URL Pattern**: `/world/:sections/:slug/`
**Structure**:
```
world/
├── _index.md                    # Main world overview
├── geography/
│   ├── _index.md               # Geography section index
│   └── kebara.md               # Individual location pages
├── religions/
│   ├── _index.md               # Religions section index
│   └── divinity-overview.md    # Religious content
├── factions/
│   ├── _index.md               # Factions section index
│   └── orden-llama-plateada.md # Organization details
└── species/
    ├── _index.md               # Species section index
    └── humanoid-species.md     # Species descriptions
```

**Content Characteristics**:
- Highly structured reference material
- Long-form descriptive content
- Hierarchical organization by topic
- Stable, rarely changing content
- Cross-referenced extensively
- Source material for adventures and campaigns

#### 2. **Adventure Modules** (`/content/adventures/`)
**Purpose**: Reusable story modules tied to specific locations, events, or threats
**URL Pattern**: `/adventures/:slug/`
**Structure**:
```
adventures/
├── _index.md                           # Adventures overview page
├── amenaza-de-la-medusa/              # Adventure module
│   ├── _index.md                      # Adventure overview & hooks
│   ├── background.md                  # Historical context & lore
│   ├── locations.md                   # Key locations involved
│   ├── npcs.md                       # Important NPCs & antagonists
│   ├── events.md                     # Major events & timeline
│   ├── factions.md                   # Organizations involved
│   └── resources/                    # Maps, handouts, etc.
├── puerto-mono-intrigue/             # Another adventure module
│   ├── _index.md
│   ├── investigation-hooks.md
│   └── faction-conflicts.md
└── orden-llama-plateada-origins/     # Faction-focused adventure
    ├── _index.md
    └── recruitment-scenarios.md
```

**Content Characteristics**:
- Location and event-focused narrative frameworks
- Reusable by multiple campaigns
- GM-facing preparation materials
- Cross-references world lore extensively
- Adaptable story structures
- Rich in NPCs, locations, and plot hooks

#### 3. **Campaign Management** (`/content/campaigns/`)
**Purpose**: Character-driven journeys and actual play documentation
**URL Pattern**: `/campaigns/:sections/:slug/`
**Structure**:
```
campaigns/
├── _index.md                          # Campaigns overview
├── escort-crew-campaign/             # Specific character group
│   ├── _index.md                     # Campaign overview
│   ├── characters/                   # Player characters & companions
│   │   ├── _index.md                # Character roster
│   │   ├── lord-besir.md            # Individual character details
│   │   └── imowen.md
│   ├── sessions/                     # Actual play logs
│   │   ├── _index.md                # Session index
│   │   ├── chapter-1-departure.md   # Session recaps
│   │   └── session-3-socavon.md
│   ├── prep/                        # GM preparation materials
│   │   ├── plot-threads.md          # Ongoing storylines
│   │   └── npc-relationships.md     # Relationship tracking
│   └── timeline.md                  # Campaign chronology
└── northern-explorers/              # Another campaign
    ├── _index.md
    ├── characters/
    └── sessions/
```

**Content Characteristics**:
- Character-centric organization
- Chronological session documentation
- Living documents that grow over time
- Actual play records and outcomes
- Character development tracking
- Campaign-specific interpretations of adventures

#### 3. **Blog Posts** (`/content/post/`)
**Purpose**: Development logs, planning notes, and miscellaneous content
**URL Pattern**: `/p/:slug/`
**Structure**:
```
post/
├── Puerto-mono/
│   └── index.md                # Session planning content
├── Villa-Cala-precuela/
│   └── index.md                # Prequel content
├── geo_kebara/
│   └── index.md                # Geographic posts
├── la-orden-del-la-llama-plateada/
│   ├── index.md                # Organization main post
│   ├── Liderazgos-y-alianzas.md
│   ├── proposito-y-operaciones.md
│   └── Redursos-y-metodologia.md
└── campaign_1/
    ├── chapter-1.md            # Legacy campaign content
    ├── Session-3.md
    └── [other session files]
```

**Content Characteristics**:
- Informal development and planning content
- Mixed organizational structure
- Legacy content from site evolution
- Blog-style posts with dates
- Planning and brainstorming materials

#### 4. **Mechanics & Rules** (`/content/mechanics/` & `/content/rules/`)
**Purpose**: Game rules, house rules, and mechanical systems
**URL Pattern**: Various (needs standardization)
**Structure**:
```
mechanics/
└── _index.md                   # Mechanics overview

rules/
└── _index.md                   # Rules overview
```

**Content Characteristics**:
- Rule definitions and clarifications
- House rules and modifications
- Reference material for gameplay
- Technical/mechanical content

#### 5. **Static Pages** (`/content/page/`)
**Purpose**: Site infrastructure and general information pages
**URL Pattern**: `/:slug/`
**Structure**:
```
page/
├── intro/
│   ├── index.md                # Site introduction (English)
│   └── index.es.md             # Site introduction (Spanish)
└── mechanics-and-house-rules/
    └── index.md                # Rules page
```

**Content Characteristics**:
- Site navigation and introduction content
- Multi-language support
- Static reference pages
- Infrastructure content

## Current Issues and Inconsistencies

### 1. **Content Duplication**
- Similar content exists in multiple locations (`/post/campaign_1/` vs `/adventures/`)
- Some world content appears in both `/world/` and `/post/` directories

### 2. **Inconsistent Organization**
- Campaign content split between `/post/` and `/adventures/`
- Some geographic content in `/post/` instead of `/world/geography/`
- Mixed organizational principles (topical vs chronological)

### 3. **URL Pattern Conflicts**
- Adventures permalink was `/a/:sections/:slug/` but navigation expected `/adventures/`
- Inconsistent depth levels across content types

### 4. **Language Mixing**
- Content in Spanish and English mixed within same directories
- Inconsistent language tagging and organization

## Taxonomies

### Current Taxonomies (config.yaml)
```yaml
taxonomies:
  category: categories
  tag: tags
  location: locations
  faction: factions
```

### Common Categories
- `geography` - Geographic content
- `Adventure Session` - Session logs and planning
- `Planificación de Campaña` - Campaign planning (Spanish)

### Common Tags
- Location names (`Puerto Mono`, `Kebara`)
- Campaign identifiers (`Amenaza de la Medusa`, `The Escort Crew`)
- Content types (`Worldbuilding`, `Session Planning`)

## Navigation Structure

### Main Menu Items
```yaml
# English
- World (/world/)
- Adventures (/adventures/)
- Mechanics (/mechanics/)

# Spanish
- Mundo (/world/)
- Aventuras (/adventures/)
- Mecánicas (/mechanics/)
```

### URL Patterns (Updated)
```yaml
permalinks:
  post: /p/:slug/
  page: /:slug/
  world: /world/:sections/:slug/
  adventures: /adventures/:slug/
  campaigns: /campaigns/:sections/:slug/
```

**Resulting URL Examples**:
- `/world/geography/kebara/` - World reference material
- `/adventures/amenaza-de-la-medusa/` - Adventure module overview
- `/campaigns/escort-crew-campaign/sessions/chapter-1/` - Session logs
- `/campaigns/escort-crew-campaign/characters/lord-besir/` - Character details

## Implementation Plan

### Phase 1: Structure Creation
1. **Create new campaigns directory structure**
2. **Update permalink configuration**
3. **Add campaigns to navigation menu**
4. **Create taxonomy for adventure modules and campaigns**

### Phase 2: Content Migration
1. **Separate adventure modules from campaign content**
   - Extract "Amenaza de la Medusa" story elements → `/adventures/amenaza-de-la-medusa/`
   - Move session logs and character content → `/campaigns/escort-crew-campaign/`
2. **Migrate world content from posts**
   - Move geographic content to `/world/geography/`
   - Move faction content to `/world/factions/`
3. **Clean up legacy post structure**

### Phase 3: Cross-referencing
1. **Link adventures to campaigns** that have used them
2. **Link world content** to relevant adventures and campaigns
3. **Update internal navigation** and menus
4. **Add content relationship metadata**

### Content Migration Strategy

#### Current → New Structure Mapping
```
# Adventure Module Content
current: /adventures/campaign-2-amenaza-de-la-medusa/_index.md
new:     /adventures/amenaza-de-la-medusa/_index.md

current: /adventures/campaign-2-amenaza-de-la-medusa/sessions/eventos-organizaciones.md
new:     /adventures/amenaza-de-la-medusa/background.md

# Campaign Content
current: /adventures/campaign-1-the-escort-crew/
new:     /campaigns/escort-crew-campaign/

current: /post/campaign_1/
new:     /campaigns/escort-crew-campaign/sessions/

# World Content
current: /post/la-orden-del-la-llama-plateada/
new:     /world/factions/orden-llama-plateada/

current: /post/geo_kebara/
new:     /world/geography/kebara/
```

## Taxonomy Updates

### New Taxonomies
```yaml
taxonomies:
  category: categories
  tag: tags
  location: locations
  faction: factions
  adventure: adventures    # Links content to adventure modules
  campaign: campaigns      # Links content to specific campaigns
```

### Content Relationships
- **Adventures** can reference multiple **locations** and **factions**
- **Campaigns** can utilize multiple **adventures**
- **World** content feeds into both **adventures** and **campaigns**
- **Session logs** belong to specific **campaigns** but may reference **adventures**

## Benefits of New Structure

1. **Clear Content Separation**: Adventure modules vs actual play documentation
2. **Content Reusability**: Adventure modules can be used by multiple campaigns
3. **Better Organization**: Character-driven vs location-driven content split
4. **Scalability**: Easy to add new campaigns without mixing content types
5. **Cross-referencing**: Clear relationships between world lore, adventures, and campaigns

---

*This specification should be updated as the site structure evolves and new content patterns emerge.*