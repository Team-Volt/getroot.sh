# Root Shell design system

## 0. Research log

Embedded references: shortlisted Vercel, Supabase, and Linear; selected minimalist execution and Vercel's compressed display typography, monospace labels, generous whitespace, and precise surface edges. The requested Linux theme supplies the dark palette and green prompt.

Lazyweb and StyleGallery were unreachable in this execution environment. Image concepts are outside the requested basic static splash scope; the focal object is a typeset shell session, implemented in HTML rather than a raster asset.

## 1. Atmosphere and identity

A quiet Linux workstation with a large, confident editorial headline. The signature is an oversized root prompt alongside a readable shell session. Green identifies the prompt and command output, not a claim about production status. No fictional customers, contacts, products, or links.

## 2. Color

Canvas #0c0f0d; terminal #101612; raised chrome #171e19; primary ink #edf2ed; secondary ink #a6b3a8; muted ink #829386; accent #b6ed91; dark accent #172313; rule #2b372e; focus #d0ffb0. Selection uses accent with canvas ink. The restrained terminal edge and inset highlight adapt Vercel's layered edge treatment.

## 3. Typography

Display and body use system sans: Helvetica Neue, Arial, sans-serif. Technical text uses SFMono-Regular, Consolas, Liberation Mono, monospace. No downloaded fonts. Display 88px desktop, fluid 44–88px, weight 500, tracking -0.065em, line height 1.02. Body 18px/1.65; section heading 28px/1.2; technical labels 12px/1.5; shell content 14px/1.8; small copy 14px/1.6.

## 4. Layout and spacing

Document owns scrolling. Container maximum 1200px, desktop gutters 48px, mobile 24px. Spacing scale 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96px. Header and footer are compact ruled rows. Hero uses an asymmetric two-column composition, collapsing to source-order single column below 900px. Capabilities use three equal columns above 720px and simple ruled rows below. No fixed hero height or nested scrolling. Terminal text wraps on narrow devices.

## 5. Primitives and states

Prompt mark: typographic # and underline; decorative repetitions hidden from assistive technology. Text link: normal muted ink, hover primary ink and underline, visible 2px focus outline, minimum 44px touch area. Action link: accent fill with dark ink; hover primary fill; active unchanged geometry; visible focus. Shell panel: 8px radius, subtle edge, inset highlight, readable text and no pretend input. Capability row: numbered mono label, descriptive heading, short body. Skip link: hidden until focused, then visible above header. Equivalent state harness is the actual page at desktop, tablet, mobile, and keyboard focus.

## 6. Depth and motion

Flat page; only terminal uses inset edge and a small ambient shadow. No decorative blur, gradients, cursor effects, automatic animation, or typing simulation. Hover color transitions 160ms. Smooth anchor scrolling only when reduced motion is not requested; reduced-motion removes transitions and uses instant scrolling.

## 7. Responsive and accessibility constraints

Semantic header/nav/main/section/footer; single h1; real fragment links; descriptive navigation; terminal readable as text; no screen-reader announcement of decorative prompt art. Visible keyboard focus, strong text contrast, minimum 44px action targets, usable at 320px and zoomed text. No essential content conveyed by color alone.

## 8. Content and accepted limitations

Visitors should understand that Root Shell LLC builds software and AI products and provides technology consulting. The site has no contact CTA because no verified public contact address was supplied. The owner approved public source and GitHub Pages hosting. Domain DNS changes remain the owner's responsibility. Verify deployment and custom-domain HTTPS independently.
