# Krita Custom Workflow Guide

This directory contains custom workflow configurations for Krita-ComfyUI integration. These workflows allow you to design node graphs in ComfyUI and run them directly from Krita.

## Available Nodes

### Core Nodes

#### 1. Krita Output Node
- The most essential node for workflow synchronization
- Enables Krita to receive images from ComfyUI
- Replaces standard `Save Image` or `Preview Image` nodes
- Supports multiple outputs and batch image processing
- Can handle various image resolutions and formats

#### 2. Krita Canvas Node
- Provides information about the Krita document/canvas
- Features:
  - Access to current visible image content
  - Canvas resolution information
  - Integration with Krita's document structure

### Parameter Management

#### 3. Parameter Node
- Exposes adjustable parameters in the Krita interface
- Creation: Right-click node > "Convert Widget to Input"
- Organization features:
  - Numeric prefixes for ordering (e.g., "1. ", "2. ")
  - Group creation using "/" (e.g., "My Group/My Parameter")
  - Non-nested grouping support

### Layer Management

#### 4. Layer-related Nodes
- **Krita Image Layer**: RGB layer selection and manipulation
- **Krita Mask Layer**: Selection and transparency mask handling
- **Krita Selection**: Current selection reading and mask creation

### Style and Configuration

#### 5. Krita Style Node
- Model and settings management:
  - Checkpoint loading
  - Diffusion model configuration
  - GGUF model support
- Additional features:
  - Clip and VAE integration
  - LoRA support
  - Model settings (e.g., clip skip)

#### 6. Send Text Node
- Enables text information transmission to the plugin
- Supports various text-based operations and configurations

## Workflow Usage

### Setup and Configuration
1. Import workflow files (JSON format)
2. Ensure at least one `Krita Output` node exists
3. Design in ComfyUI's Web interface
4. Execute directly from Krita

### Important Considerations
- Resolution requirements:
  - Diffusion model outputs must be multiples of 8, 16, or 64
  - May require cropping or resizing before `Krita Output`
- Parameter organization:
  - Groups cannot be nested
  - Order is determined by numeric prefixes
- Sampler compatibility:
  - Some samplers (e.g., AlignYourSteps) need explicit workflow modeling

## Example Workflow

The `Custom.Workflow.Example.json` file in this directory demonstrates:
1. Basic node configuration
2. Parameter setup
3. Canvas integration
4. Image processing pipeline

### Key Components:
- `ETN_KritaCanvas`: Canvas management
- `EmptyLatentImage`: Initial image generation
- `CLIPTextEncode`: Text prompt processing
- `KSampler`: Image sampling and generation

## Getting Started

1. Import the example workflow
2. Customize parameters as needed
3. Connect to your ComfyUI instance
4. Execute the workflow from Krita

## Additional Resources

For more detailed information, visit:
- [Custom Workflows Documentation](https://github.com/Acly/krita-ai-diffusion/wiki/Custom-Workflows#custom-workflow-guide)
- [Krita-AI-Diffusion Repository](https://github.com/Acly/krita-ai-diffusion)

## Requirements

- Krita with AI plugin (version 1.26.0 or later)
- ComfyUI server installation (managed or custom)
- Basic understanding of ComfyUI and image diffusion technology
