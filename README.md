# Healthcare Sales Intelligence Platform

> AI-powered sales intelligence platform for healthcare sales recruiters managing thousands of contacts across hundreds of companies.

![Platform Status](https://img.shields.io/badge/status-in%20development-yellow)
![Tech Stack](https://img.shields.io/badge/stack-Next.js%2015%20%7C%20TypeScript%20%7C%20Supabase%20%7C%20Prisma-blue)
![License](https://img.shields.io/badge/license-Private-red)

## 🎯 Overview

This platform provides AI-powered sales intelligence through 6 specialized agents while integrating with GoHighLevel (primary), multiple CRMs, and ATS platforms. Built for solo healthcare sales recruiters managing 100s of companies and 1000s of contacts with a budget of $150-300/month operational costs.

### 🚀 Current Features

- ✅ **Professional Dashboard** - Real-time stats, intelligence alerts, hot prospects
- ✅ **Complete Database Schema** - Companies, contacts, intelligence reports, activities
- ✅ **Supabase Integration** - Production-ready PostgreSQL database
- ✅ **Modern Tech Stack** - Next.js 15, TypeScript, Prisma ORM
- ✅ **Responsive Design** - Mobile-first approach with Tailwind CSS
- ✅ **MCP Integration** - Supabase Model Context Protocol for AI operations

### 🔮 Planned AI Intelligence Agents

1. **Executive Intelligence Agent** - Track C-suite and VP movements
2. **Market Research Agent** - Generate 5-7 page business cases
3. **Talent Intelligence Agent** - Analyze sales team movements
4. **Regulatory Impact Agent** - Monitor government decisions and healthcare policy
5. **Compensation Intelligence Agent** - Track executive compensation and valuations
6. **Competitive Intelligence Agent** - Build competitive matrices and monitor launches

## 🛠 Tech Stack

### Frontend
- **Framework**: Next.js 14 with App Router
- **Language**: TypeScript (strict mode)
- **Styling**: Tailwind CSS + shadcn/ui components
- **State Management**: Zustand for global state
- **Forms**: React Hook Form + Zod validation
- **Charts**: Recharts for data visualization
- **Real-time**: Supabase real-time subscriptions

### Backend
- **Database**: Supabase (PostgreSQL) with Row Level Security
- **ORM**: Prisma with type generation
- **Cache**: Upstash Redis for performance (planned)
- **Jobs**: BullMQ for background processing (planned)
- **Search**: PostgreSQL full-text search with indexes
- **Vector**: Supabase Vector for semantic search (planned)
- **File Storage**: Supabase Storage for CSV uploads (planned)

### AI & Integrations
- **AI Provider**: Claude 3.5 Sonnet (Anthropic API)
- **Embeddings**: OpenAI text-embedding-3-small (planned)
- **Primary CRM**: GoHighLevel API integration (planned)
- **Secondary CRMs**: Salesforce, HubSpot, Pipedrive adapters (planned)
- **ATS**: Bullhorn, JobDiva, PCRecruiter integrations (planned)
- **Deployment**: Vercel with serverless functions

## 📁 Project Structure

```
healthcare-sales-intelligence/
├── apps/
│   └── web/                          # Next.js frontend
│       ├── app/
│       │   ├── dashboard/            # Main recruiter dashboard
│       │   │   ├── layout.tsx        # Dashboard navigation
│       │   │   └── page.tsx          # Dashboard overview
│       │   ├── globals.css
│       │   ├── layout.tsx            # Root layout
│       │   └── page.tsx              # Homepage (redirects to dashboard)
│       ├── prisma/
│       │   └── schema.prisma         # Complete database schema
│       └── package.json
├── packages/                         # Shared packages (planned)
├── prisma/                          # Database configuration
├── .env                             # Environment variables
├── .gitignore                       # Git ignore rules
└── README.md                        # This file
```

## 🗄 Database Schema

### Core Entities
- **Companies** - Healthcare organizations with size, revenue, industry data
- **Contacts** - Sales prospects with titles, seniority, decision-maker status
- **Intelligence Reports** - AI-generated insights with confidence scores
- **Activities** - Sales interactions and follow-ups
- **CRM Integrations** - Multi-CRM sync configuration
- **Bulk Operations** - Mass contact processing and imports

### Advanced Features
- **Full-text search** with PostgreSQL indexes
- **Multi-CRM ID tracking** (GoHighLevel, Salesforce, HubSpot)
- **Lead scoring** and pipeline management
- **AI confidence scoring** for intelligence reports
- **Audit trails** and activity tracking

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ and npm
- Supabase account and project
- Git for version control

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/nmartin15/businessdevelopmentbot2.git
   cd businessdevelopmentbot2
   ```

2. **Install dependencies**
   ```bash
   cd apps/web
   npm install
   ```

3. **Set up environment variables**
   ```bash
   # Copy example env file
   cp .env.example .env
   
   # Add your actual values:
   NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your_anon_key
   SUPABASE_SERVICE_ROLE_KEY=your_service_role_key
   DATABASE_URL="postgresql://postgres:password@db.project.supabase.co:6543/postgres?pgbouncer=true"
   ```

4. **Set up database**
   ```bash
   npx prisma generate
   npx prisma db push
   ```

5. **Start development server**
   ```bash
   npm run dev
   ```

6. **Visit the application**
   - Open [http://localhost:3000](http://localhost:3000)
   - You'll be redirected to `/dashboard`

## 📊 Current Dashboard Features

### Statistics Overview
- **Total Contacts**: Track your prospect database size
- **Companies**: Monitor healthcare organizations 
- **Urgent Alerts**: AI-flagged high-priority items
- **Pipeline Value**: Total deal value in progress

### Intelligence Alerts
- **Executive Movement**: Leadership changes and opportunities
- **Funding News**: Series rounds and expansion signals
- **Market Research**: Regulatory impacts and market shifts

### Hot Prospects
- **Match Scoring**: AI-powered prospect ranking
- **Last Contact**: Track engagement recency
- **Decision Maker Status**: Identify key stakeholders

### Quick Actions
- **Generate Intelligence**: Run AI analysis on prospects
- **Import Contacts**: CSV upload and CRM sync
- **View Reports**: Sales analytics and insights

## 🔧 Development

### Key Commands
```bash
# Start development server
npm run dev

# Build for production
npm run build

# Run database migrations
npx prisma migrate dev

# Generate Prisma client
npx prisma generate

# View database
npx prisma studio
```

### Adding New Features
1. **Database changes**: Update `prisma/schema.prisma`
2. **Frontend pages**: Add to `app/` directory
3. **API routes**: Create in `app/api/` directory
4. **Components**: Build in `components/` directory

## 🌟 Roadmap

### Phase 1: Foundation ✅
- [x] Project setup with Next.js 14 + TypeScript
- [x] Supabase database schema and Prisma setup
- [x] Basic dashboard and navigation
- [x] Core contact and company management UI

### Phase 2: Intelligence Engine (In Progress)
- [ ] RSS feed aggregation system
- [ ] Government API integrations (FDA, CMS, SEC)
- [ ] AI agent framework with Claude integration
- [ ] Background job processing with BullMQ
- [ ] Real-time intelligence notifications

### Phase 3: CRM Integration (Planned)
- [ ] GoHighLevel primary integration
- [ ] Multi-CRM adapter framework
- [ ] Webhook handling for real-time sync
- [ ] Bulk operation processing
- [ ] Conflict resolution for duplicate data

### Phase 4: Advanced Features (Planned)
- [ ] CSV upload with intelligent field mapping
- [ ] Advanced search with full-text indexing
- [ ] Mobile-responsive interface optimization
- [ ] ATS integration for candidate management
- [ ] Performance optimization and caching

## 📈 Performance Targets

### Technical KPIs
- **Search Response**: <500ms for 10,000+ contacts
- **Bulk Processing**: 1000 contacts/minute
- **Real-time Updates**: <2 seconds latency
- **System Uptime**: 99.9%
- **AI Processing Cost**: <$200/month

### Business KPIs
- **Lead Qualification**: 15%+ improvement in accuracy
- **Sales Cycle**: 20%+ reduction in length
- **Contact Engagement**: 25%+ increase in rates
- **Pipeline Growth**: Monthly value tracking

## 🔒 Security & Privacy

- **Environment Variables**: All sensitive data in `.env` (gitignored)
- **Database Security**: Supabase Row Level Security enabled
- **API Keys**: Secure token management
- **Data Privacy**: Healthcare-compliant data handling

## 🤝 Contributing

This is a private project for healthcare sales intelligence. For questions or collaboration:

1. **Issues**: Use GitHub Issues for bug reports
2. **Features**: Discuss via GitHub Discussions
3. **Code**: Follow TypeScript and React best practices
4. **Database**: Always use migrations for schema changes

## 📄 License

Private - All rights reserved. This project contains proprietary healthcare sales intelligence algorithms and integrations.

## 📞 Support

For technical support or questions:
- **GitHub Issues**: Bug reports and feature requests
- **Documentation**: Check this README and inline code comments
- **Database**: Use Prisma Studio for data inspection

---

**Built with ❤️ for healthcare sales professionals**

*Last updated: June 2025*
