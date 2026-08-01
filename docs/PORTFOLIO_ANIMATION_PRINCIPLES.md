# Portfolio Animation Principles — Version 1

## 1. Purpose and scope

Motion should support hierarchy and orientation, clarify interaction feedback, and make transitions feel polished. It must remain restrained and optional: it cannot compensate for weak layout or content, and it must not become the main evidence of frontend ability.

This document records approved Version 1 direction for future work. It does not authorize animation implementation or application-code changes.

## 2. Core principles

- Give every motion choice a communication purpose. Remove motion that only calls attention to itself.
- Prefer restraint, consistency, short durations, subtle distances, and subtle scale changes over spectacle.
- Apply the same motion behavior to similar interactions and components.
- Keep all essential information visible and all navigation and comprehension independent of motion.
- Treat accessibility and `prefers-reduced-motion` support as requirements, not optional polish.
- Use progressive enhancement so content and controls remain complete when JavaScript or animation is unavailable.
- Protect performance, particularly on lower-powered mobile devices.
- Never use animation to imply that a project is more complete, interactive, deployed, or mature than the approved content supports.

The intended result is polished and modern, not animation-heavy.

## 3. Approved motion categories

| Category | Status and purpose | Suitable properties | Unsuitable effects | Accessibility and reduced motion |
| --- | --- | --- | --- | --- |
| Direct interaction feedback | **Required.** Confirm hover, active, and other state changes. | Color, background color, border color, underline thickness or offset, subtle shadow, and very small translation. | Large scale, bounce, pulse, rotation, elastic motion, or layout movement. | State must remain perceivable without motion. Focus-visible is immediate. Reduced motion keeps clear state changes with no or near-zero movement. |
| Navigation disclosure | **Conditional.** Clarify an open or closing mobile menu only if layout testing justifies a disclosure. | Opacity and small translation; a restrained visibility transition. | Theatrical full-screen movement, spinning controls, or motion-dependent availability. | State, focus, keyboard behavior, and control attributes must stay synchronized. Reduced motion makes disclosure immediate or nearly immediate. |
| In-page anchor movement | **Optional.** Provide spatial continuity between an anchor link and its target. | Native browser smooth scrolling as progressive enhancement. | Custom scroll physics, scroll-jacking, delayed arrival, or a custom scrolling library. | Native instant navigation is the baseline; reduced motion uses instant scrolling. |
| Section-entry reveals | **Optional.** Gently establish hierarchy for selected major sections or evidence. | Opacity with a small vertical translation. | Reveal dependency, large travel, scale-heavy entrances, long staggers, or per-item choreography. | Content is present without JavaScript. Reduced motion shows it immediately. |
| Project-image or evidence transitions | **Conditional.** Support inspection or context when multiple approved visuals or a genuine image destination exist. | Opacity, border or shadow change, and a simple crossfade or short translation between approved images. | Autoplay, automatic carousels, fake interactions, looping mockups, parallax, or dramatic device movement. | Controls require names, keyboard access, visible focus, and understandable state. Reduced motion uses direct replacement or a near-instant fade. |
| Status and label behavior | **Required as static communication; motion not justified.** Preserve accurate maturity information. | Immediate color, border, or background state only if the label later becomes interactive for a real reason. | Blinking, pulsing, warning animation, or celebratory motion. | Status remains explicit text and never depends on color or motion. |
| Signature interaction | **Deferred.** Add one meaningful, memorable interaction only after its exact purpose is approved. | To be decided from the verified interaction requirement. | Decorative spectacle, inaccessible interaction, or maturity-exaggerating simulation. | It must remain understandable with reduced motion or provide an accessible static alternative. |

## 4. Interaction feedback

Links, buttons, navigation items, and the mobile-menu toggle should use restrained combinations of color, background color, border color, underline thickness or offset, a very small translation, or a subtle shadow or elevation change. Active feedback may suggest a slight press without shifting nearby content.

Interactive cards are conditional and may receive the same restrained boundary or elevation treatment only if a later approved whole-card destination justifies interactivity. They must not reveal essential information only on hover.

Avoid large scaling, bouncing, repeated pulsing, dramatic rotation, elastic motion, hover-only information, and effects that move text or change layout. Focus-visible feedback must be immediate, distinct on every approved surface, and independent of animation.

## 5. Navigation and menu motion

Always-visible or naturally wrapped navigation remains preferred. If mobile layout testing justifies a disclosure, opening and closing may use a short, consistent ease-out transition with limited opacity or translation. The close behavior should be no slower than the open behavior, and the menu must not use a full-screen theatrical transition unless a later verified requirement justifies it.

The toggle state, visible menu state, `aria-expanded`, and `aria-controls` relationship must agree. Opening places links in the normal keyboard sequence. Escape closes an expanded menu and returns focus to the toggle; closing also returns focus when focus would otherwise remain in hidden content. Selecting an in-page link closes the menu without trapping focus.

Navigation links should remain available without JavaScript wherever practical, with enhancement applied only after the control is operational. Reduced motion makes disclosure immediate or nearly immediate. No JavaScript-heavy navigation system or scroll-spy behavior is required.

## 6. In-page scrolling

Native instant anchor navigation is the Version 1 baseline. Smooth scrolling is optional progressive enhancement and must respect `prefers-reduced-motion`, never delay access to the target, and never become necessary for orientation or navigation.

Anchored headings must remain visible after navigation. If sticky navigation is later adopted, target spacing must prevent header overlap. No custom scroll library is justified.

## 7. Section-entry animation

Major section containers and selected project evidence may be eligible for one restrained entry reveal. Essential headings, the header and navigation, hero identity and primary actions, status information, and content needed to understand the page should appear immediately.

An eligible reveal may combine opacity with only a small vertical translation, approximately no more than 8–16 CSS pixels. It should normally run once on first viewport entry. Content near the initial viewport should not wait for an observer, and content must not flash from visible to hidden during setup.

Do not animate every paragraph, badge, skill, entry, or action. Avoid long stagger sequences and repeated animations as the user scrolls back and forth. With JavaScript unavailable or reduced motion requested, all content appears immediately in its final position. No library is prescribed.

## 8. Project evidence and image motion

Motion around MediCheck screenshots and future EchoTask visuals is allowed only when it helps inspection or context. Appropriate uses are a subtle hover or focus treatment on a genuine image link, a simple user-controlled transition between approved screenshots, or a later accessible media viewer if evidence and usability justify it.

Do not use automatic carousels, autoplay, looping mockup motion, fake application interactions, exaggerated device movement, readability-reducing parallax, or motion that suggests a completed or deployed product. MediCheck may receive slightly stronger presentation emphasis through scale, spacing, and evidence depth, but not more aggressive motion.

EchoTask must retain the exact visible label `Interface preview in development.` The label must not pulse, blink, or use warning-style animation.

## 9. Timing and easing guidance

Use only a few semantic timing categories:

| Category | Approximate range | Guidance |
| --- | --- | --- |
| Immediate state feedback | 0–100 ms | Focus-visible and state changes where delay would reduce clarity. |
| Short interaction transition | 100–180 ms | Link, button, navigation-item, and pressed feedback. |
| Standard component transition | 160–240 ms | Mobile disclosure or a user-controlled evidence change. |
| Optional section reveal | 200–350 ms | A selective one-time entrance with no long delay. |

Prefer standard ease-out or a similarly natural easing for entrances and interaction feedback. Avoid long delays, decorative stagger chains, spring or elastic easing, inconsistent timing for similar components, and transitions longer than their communication purpose requires. Version 1 does not need a large motion-token system.

## 10. Reduced-motion requirements

When `prefers-reduced-motion: reduce` is active:

- Remove or nearly remove nonessential translation, scale, parallax, and smooth scrolling.
- Make state changes immediate or very short while retaining clear visual feedback.
- Preserve all content, state, focus, and orientation.
- Keep menus fully operable and make section content appear without reveal dependency.
- Keep the signature interaction understandable or provide an accessible static alternative.
- Do not autoplay or loop motion.

Reduced motion does not mean removing all visual state feedback. Color, underline, border, focus outline, and other immediate non-motion cues remain necessary.

## 11. Performance and implementation constraints

Future implementation should prefer CSS transitions and animations for simple effects, use compositor-friendly properties where practical, and avoid layout-triggering animation, unnecessary scroll listeners, and large client-side bundles. An animation library is not justified unless a later verified requirement cannot be met simply and accessibly.

Motion must preserve Astro's lightweight static architecture and work acceptably on lower-powered mobile devices. Do not add React or another framework for animation.

## 12. Motion inventory

| Likely use | Version 1 classification | Direction |
| --- | --- | --- |
| Link and button state transitions | Required | Short, restrained, and structurally stable. |
| Focus-visible state | Required | Immediate; no animation dependency. |
| Mobile-menu disclosure | Conditional | Only if mobile layout requires a disclosure. |
| Smooth anchor scrolling | Optional | Native instant anchors remain the baseline. |
| Section-entry reveal | Optional | Selective, one-time, and progressively enhanced. |
| Project-image transition | Conditional | User-controlled and tied to approved evidence. |
| Current-section scroll spy | Not justified | Static anchor navigation is sufficient. |
| Decorative background animation | Not justified | Adds no approved communication value. |
| Autoplay carousel | Not justified | Automatic motion and access barriers conflict with Version 1. |
| Parallax | Not justified | Risks readability, performance, and unnecessary motion. |
| Signature interaction | Deferred | Define its purpose and accessible fallback later. |

## 13. Deferred decisions

- The exact signature interaction.
- Implementation-specific motion tokens.
- Exact section-reveal eligibility.
- Final screenshot-viewer behavior.
- Detailed mobile-layout interactions.
- The final implementation technique after the layout is approved.
