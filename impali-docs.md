# Impali Primary School E-Learning Platform Documentation

**Last updated**: 30 January 2025

---

## Technical Specifications

- **Ruby Version**: 3.0.0
- **Rails Version**: 6.1.7
- **Database**: PostgreSQL 15
- **Key Dependencies**:

  | Dependency | Version | Purpose          |
  |------------|---------|------------------|
  | Devise     | 4.8.1   | Authentication   |
  | Sidekiq    | 6.5.8   | Background Jobs  |
  | Redis      | 4.8.0   | Caching/Jobs     |

---

## Setup Instructions

### Fresh Environment Setup

```bash
# Install dependencies
bundle install

# Database setup
rails db:create
rails db:migrate
rails db:seed

# Start server
rails server
```

### Environment Variables

```bash
DATABASE_URL=postgresql://user:password@localhost/impali2024
SECRET_KEY_BASE=your-rails-secret-key
REDIS_URL=redis://localhost:6379/1
```

---

## Deployment Guide

### Requirements

- Ubuntu 20.04+ Server
- 2GB RAM minimum
- PostgreSQL 13+
- Redis 6+

### Production Deployment

```bash
git clone https://github.com/ttchikasha/impali2024.git
bundle install --without development test
RAILS_ENV=production rails assets:precompile
bundle exec sidekiq -e production
```

---

## Security Notes

- Reset all test credentials from `seeds.rb`.
- Rotate `SECRET_KEY_BASE` before redeployment.
- Domain ownership maintained by Gigasoft Group.

---

## Contact

**Gigasoft Group Support**  
📧 [admin@gigasoft.group](mailto:admin@gigasoft.group)  
📞 [+263 772 771 375](tel:+263772771375) | [+263 719 771 375](tel:+263719771375)
