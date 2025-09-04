---
title: 'Pruebas UX/UI '
excerpt: 'Ambiente para probar las mejoras que implementará el equipo de UX/IU. '
deprecated: false
hidden: true
metadata:
  robots: index
---
```
ggg
```

<HTMLBlock>{`
<button>hola</button>
`}</HTMLBlock>

<Button variant="primary" text="click" />

```cplusplus
console
sdad
sdasd
```
```javascript
export const Button = ({
    /* text of the button */
    text,
    /* primary | secondary */
    variant = "primary",
    /* sm | md | lg */
    size = "md",
    /* full width */
    full = false,
    /* disabled state */
    disabled = false,
    /* icon */
    icon = "",
    /* link */
    href = "",
    /* link target */
    target = "_self"
}) => {
    const classes = [
        "pp-btn",
        `pp-btn--${variant}`,
        `pp-btn--${size}`,
        full ? "pp-btn--full" : "",
        disabled ? "is-disabled" : "",
    ].join(" ");

    const Component = href ? "a" : "button";

    return (
        <Component className={classes} disabled={disabled} href={href} target={target}>
            <span className="pp-btn__label">{text}</span>
            {icon ? <i className={`pp-btn__icon ${icon}`} aria-hidden="true" /> : null}
        </Component>
    );
};
```

<br />

<br />

<Cards columns={2}>
  <GuideCard icon="fa-solid fa-circle-info" title="Guide Card Title" description="This is a description of the guide card." />

  <GuideCard icon="fa-solid fa-circle-info" title="Guide Card Title" description="This is a description of the guide card." />
</Cards>

<Cards columns={2}>
  <ImageCard imageSrc="https://via.placeholder.com/150" imageAlt="Placeholder Image" title="Card Title" description="This is a description of the card." />
</Cards>

<Button variant="secondary" text="click" icon="fa-solid fa-arrow-up-right-from-square" />

<Cards columns={3}>
  <Card title="First Card" href="https://readme.com" icon="fa-home" target="_blank">
    Neque porro quisquam est qui dolorem ipsum quia
  </Card>

  <Card title="Second Card" icon="fa-user">
    *Lorem ipsum dolor sit amet, consectetur adipiscing elit*
  </Card>

  <Card title="Third Card" icon="fa-star">
    > Ut enim ad minim veniam, quis nostrud ullamco
  </Card>
</Cards>
