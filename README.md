# RetailerBoost Landing Page

Static landing page for RetailerBoost outbound campaigns.

## UTM Parameter Passthrough

The landing page automatically captures and passes through UTM parameters to all CTAs (both signup links and Calendly bookings).

### How It Works

1. When a visitor arrives at the page with UTM parameters (e.g., from an email campaign), the JavaScript captures them
2. All "Get Started" links pointing to `app.retailerboost.com/signup` are automatically updated with those UTM params
3. All "Book a Call" buttons pass UTM params to Calendly via the `utm` object in `Calendly.initPopupWidget()`
4. If no UTM params are present in the URL, defaults are used

### Default UTM Values

| Parameter | Default Value |
|-----------|---------------|
| `utm_source` | `retailerboostplatform.com` |
| `utm_medium` | `outbound` |
| `utm_campaign` | `email` |

### Supported UTM Parameters

- `utm_source` - Traffic source (captured or defaults to domain)
- `utm_medium` - Marketing medium (captured or defaults to "outbound")
- `utm_campaign` - Campaign name (captured or defaults to "email")
- `utm_term` - Optional, passed through if present
- `utm_content` - Appended to the page location identifier (e.g., `campaign-content_hero`)

### Example Usage

**Campaign URL:**
```
https://retailerboostplatform.com/?utm_source=apollo&utm_medium=email&utm_campaign=q1-outreach&utm_content=variant-a
```

**Resulting Signup URL:**
```
https://app.retailerboost.com/signup?utm_source=apollo&utm_medium=email&utm_campaign=q1-outreach&utm_content=variant-a_hero
```

### Page Location Identifiers

Each CTA has a location identifier appended to `utm_content`:

| Location | Identifier |
|----------|------------|
| Desktop navigation | `nav` |
| Mobile navigation | `nav-mobile` |
| Top alert banner | `alert` |
| Hero section | `hero` |
| Works Alongside section | `works-alongside` |
| Problem/Cannibalization block | `problem-block` |
| Pricing (Self-Serve) | `pricing-self-serve` |
| Footer CTA | `footer-cta` |
| Eligibility modal | `eligibility-modal` |

## Page Structure

- **Hero** - Main headline and primary CTA
- **Featured Testimonial** - Bea's quote (MenFirst)
- **Scenarios** - 4 cards explaining use cases
- **Works Alongside** - Compatibility with agencies/teams
- **Cannibalization Section** - Explains the incremental model
- **Comparison Table** - RetailerBoost vs Traditional Google Ads
- **How It Works** - Step-by-step process
- **Pricing** - Self-Serve (12%) and Enterprise options
- **FAQ** - Expandable accordion with common questions
- **Testimonials Carousel** - Customer reviews
- **About** - Company info and team
- **Footer CTA** - Final conversion opportunity

## Analytics & Tracking

- **Google Tag Manager** - GTM-WPR55HV5
- **RB2B** - Visitor identification
- **Calendly** - Meeting scheduling popups

## Files

- `index.html` - Main landing page
- `404.html` - Error page
- `terms.html` - Terms & Conditions
- `privacy.html` - Privacy Policy
- `cookies.html` - Cookie Policy
