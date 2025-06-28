# GEMINI.md - Healthcare Sales Intelligence Platform

## Project Overview

This is a healthcare sales intelligence platform built for solo recruiters managing thousands of contacts across hundreds of healthcare companies. The platform provides AI-powered sales intelligence through 6 specialized agents while integrating with GoHighLevel (primary), multiple CRMs, and ATS systems.

### Project Context
- **Target User**: Solo healthcare sales recruiter
- **Scale**: 100s of companies, 1000s of contacts
- **Budget**: $150-300/month operational costs
- **Primary Integration**: GoHighLevel CRM + ATS systems

## Tech Stack & Architecture

### Frontend
- **Framework**: Next.js 15 with App Router
- **Language**: TypeScript (strict mode)
- **Styling**: Tailwind CSS + shadcn/ui
- **State**: Zustand for global state
- **Forms**: React Hook Form + Zod validation
- **Charts**: Recharts for data visualization

### Backend
- **Database**: Supabase (PostgreSQL) with Row Level Security
- **ORM**: Prisma with type generation
- **AI Provider**: Claude 3.5 Sonnet (Anthropic API)
- **Deployment**: Vercel with serverless functions

### Project Structure
```
BusinessDevelopmentBotv2.0/
├── apps/web/                 # Next.js frontend application
│   ├── src/app/             # App Router pages
│   │   ├── dashboard/       # Main dashboard interface
│   │   ├── layout.tsx       # Root layout
│   │   └── page.tsx         # Homepage (redirects to dashboard)
│   └── prisma/schema.prisma # Database schema
├── packages/                # Shared packages (planned)
├── .env                     # Environment variables
└── README.md               # Project documentation
```

## Code Review Focus Areas

### 1. Healthcare-Specific Requirements
When reviewing code, pay special attention to:
- **Data Privacy**: Healthcare data handling compliance
- **Security**: Contact and company data protection
- **Performance**: Handling thousands of contacts efficiently
- **Scalability**: Supporting 100s of companies growth

### 2. Database Schema Review
- **Contact Management**: Complex relationships between contacts, companies, activities
- **Intelligence Reports**: AI-generated insights with confidence scoring
- **CRM Integration**: Multi-platform sync capabilities
- **Bulk Operations**: Mass contact processing and imports

### 3. AI Integration Points
- **6 Planned AI Agents**:
  1. Executive Intelligence Agent (leadership changes)
  2. Market Research Agent (business case generation)
  3. Talent Intelligence Agent (sales team movements)
  4. Regulatory Impact Agent (healthcare policy monitoring)
  5. Compensation Intelligence Agent (executive compensation tracking)
  6. Competitive Intelligence Agent (competitive analysis)

### 4. Performance Considerations
- **Search Performance**: <500ms for 10,000+ contacts
- **Bulk Processing**: 1000 contacts/minute target
- **Real-time Updates**: <2 seconds latency
- **Cost Efficiency**: Stay within $150-300/month budget

## Specific Review Guidelines

### TypeScript Standards
- Strict mode enabled - enforce type safety
- Use Prisma-generated types for database operations
- Implement proper error handling for API calls
- Use Zod schemas for form validation

### React/Next.js Best Practices
- App Router usage (not Pages Router)
- Server Components where possible
- Client Components only when necessary ('use client')
- Proper loading states and error boundaries

### Database & API Design
- Row Level Security implementation
- Efficient indexing for search operations
- Proper pagination for large datasets
- API rate limiting and error handling

### Security & Privacy
- Environment variable management
- API key protection
- Healthcare data compliance considerations
- Input sanitization and validation

## Common Issues to Look For

### Performance Issues
- Missing database indexes for search queries
- N+1 query problems in Prisma operations
- Inefficient React re-renders
- Large bundle sizes affecting load times

### Security Concerns
- Exposed API keys or sensitive data
- Missing input validation
- Inadequate error handling
- Potential SQL injection points

### Code Quality
- Missing TypeScript types
- Inconsistent naming conventions
- Lack of error boundaries
- Missing loading states

### Healthcare-Specific Concerns
- Data retention policies
- Contact privacy controls
- Audit trail requirements
- Compliance documentation

## Development Phases

### Phase 1: Foundation ✅ (Current)
- Next.js 15 + TypeScript setup
- Supabase database schema
- Basic dashboard interface
- Prisma ORM integration

### Phase 2: Intelligence Engine (Next)
- AI agent framework implementation
- RSS feed aggregation
- Government API integrations
- Background job processing

### Phase 3: CRM Integration (Planned)
- GoHighLevel primary integration
- Multi-CRM adapter framework
- Real-time sync capabilities
- Bulk operation processing

### Phase 4: Advanced Features (Future)
- CSV upload with field mapping
- Advanced search capabilities
- Mobile optimization
- ATS integration

## Review Commands

### Code Analysis
```bash
# Run type checking
npx tsc --noEmit

# Run ESLint
npm run lint

# Check for unused dependencies
npx depcheck

# Analyze bundle size
npm run build && npm run analyze
```

### Database Review
```bash
# Check schema
npx prisma format
npx prisma validate

# Review migrations
npx prisma migrate status

# Database studio
npx prisma studio
```

## AI Review Prompts

When reviewing this codebase, please consider:

1. **Healthcare Compliance**: Does this code handle healthcare contact data appropriately?

2. **Scalability**: Can this architecture handle 1000s of contacts and 100s of companies?

3. **AI Integration**: Are the AI agent integration points well-designed for the 6 planned agents?

4. **CRM Compatibility**: Is the database schema flexible enough for multi-CRM integration?

5. **Performance**: Are there any obvious performance bottlenecks for large datasets?

6. **Security**: Are there any security vulnerabilities, especially around data privacy?

7. **Code Quality**: Does the code follow TypeScript and React best practices?

8. **Maintainability**: Is the code structure clear and maintainable for future development?

## Success Metrics

### Technical KPIs
- Search response time: <500ms for 10,000+ contacts
- Bulk operation processing: 1000 contacts/minute
- Real-time update latency: <2 seconds
- System uptime: 99.9%
- AI processing cost: <$200/month

### Business KPIs
- Lead qualification accuracy: 15%+ improvement
- Sales cycle compression: 20%+ reduction
- Contact engagement rates: 25%+ increase
- Pipeline value growth: Monthly tracking

## Current Status

- ✅ **Foundation Complete**: Database, dashboard, and core infrastructure
- 🔄 **In Development**: AI agents, CRM integration, advanced features
- 📋 **Planned**: CSV upload, advanced search, mobile optimization

---

**Review Focus**: This is production-ready healthcare sales software. Please evaluate with enterprise-level standards for security, performance, and maintainability.