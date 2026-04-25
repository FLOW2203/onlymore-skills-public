---
name: composition-patterns
description: "React component composition patterns: compound components, render props, hooks, slots, headless UI. Use when architecting React components, refactoring component hierarchies, or designing reusable component APIs."
visibility: public
requires_body_cleanup: true
---
# React Composition Patterns

## 1. Compound Components
Group related components under one namespace:
```tsx
// Usage
<Card>
  <Card.Header>Title</Card.Header>
  <Card.Body>Content</Card.Body>
  <Card.Footer>Actions</Card.Footer>
</Card>

// Implementation
const CardContext = createContext({})
function Card({ children }) {
  return <CardContext.Provider value={{}}><div>{children}</div></CardContext.Provider>
}
Card.Header = ({ children }) => <div className="card-header">{children}</div>
Card.Body = ({ children }) => <div className="card-body">{children}</div>
Card.Footer = ({ children }) => <div className="card-footer">{children}</div>
```

## 2. Render Props
Pass rendering control to parent:
```tsx
<DataFetcher url="/api/merchants">
  {({ data, loading, error }) => (
    loading ? <Skeleton /> : <MerchantList merchants={data} />
  )}
</DataFetcher>
```

## 3. Custom Hooks (preferred over render props)
```tsx
// Extract logic to hooks
function useMerchant(id: string) {
  const [merchant, setMerchant] = useState(null)
  // ... fetch logic
  return { merchant, loading, error }
}

// Clean component
function MerchantCard({ id }) {
  const { merchant, loading } = useMerchant(id)
  if (loading) return <Skeleton />
  return <div>{merchant.name}</div>
}
```

## 4. Slots Pattern (via children + props)
```tsx
function Dialog({ trigger, title, children, footer }) {
  return (
    <div>
      {trigger}
      <div className="dialog">
        <h2>{title}</h2>
        <div>{children}</div>
        <div className="footer">{footer}</div>
      </div>
    </div>
  )
}
```

## 5. Headless Components
Behavior without UI — style separately:
```tsx
function useToggle(initial = false) {
  const [on, setOn] = useState(initial)
  const toggle = useCallback(() => setOn(o => !o), [])
  return { on, toggle }
}
// Caller decides the UI completely
```

## When to Use Which
| Pattern | When |
|---------|------|
| Compound | Complex widgets with shared state (Tabs, Accordion) |
| Custom Hook | Business logic reuse without UI coupling |
| Render Props | Rarely — prefer hooks instead |
| Slots | Layout components with multiple regions |
| Headless | Design system primitives |

